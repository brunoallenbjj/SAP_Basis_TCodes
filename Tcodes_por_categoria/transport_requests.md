# 📦 Gerenciamento de Transport Requests (Solicitações de Transporte)

No SAP, o sistema de **Transport Requests (TRs)** é utilizado para **mover alterações e configurações entre ambientes** — normalmente do ambiente de desenvolvimento (**DEV**) para qualidade (**QAS**) e depois para produção (**PRD**).

Esse processo é essencial para garantir a rastreabilidade, consistência e segurança das mudanças feitas no sistema, sendo um pilar fundamental para administradores BASIS, desenvolvedores ABAP e consultores funcionais.

---

## 🔧 Visão Geral das Transações

| Transação         | Função Principal |
|------------------|------------------|
| `STMS`           | Acesso ao sistema de gerenciamento de transportes (Transport Management System). |
| `SE09`           | Administração de requests do tipo Workbench (programas, objetos técnicos). |
| `SE10`           | Administração de requests de Customizing (parâmetros de negócio). |
| `STMS_IMPORT`    | Tela direta para importar requests em um ambiente de destino. |
| `SCC1`           | Copiar Customizing entre mandantes (clients) no mesmo ambiente. |
| `TP` (linha de comando) | Importação técnica e diagnósticos via sistema operacional. |
| `OS01`           | Verificação de diretórios técnicos do SAP (ex: `/usr/sap/trans`). |

---

## 📚 Detalhamento das Transações

### `STMS` – Transport Management System  
Permite configurar e gerenciar o domínio de transporte entre os ambientes. Através dessa transação é possível:

- Configurar os sistemas participantes (DEV, QAS, PRD);
- Definir rotas de transporte;
- Aprovar, importar e monitorar TRs;
- Acompanhar logs de erro e históricos de transporte.

> ✅ Utilizada principalmente pela equipe BASIS.

---

### `SE09` – Workbench Requests  
Exibe e gerencia requests do tipo **Workbench**, que armazenam alterações técnicas como:

- Programas ABAP;
- Funções e classes;
- Dicionário de dados (tabelas, domínios, etc.).

> 🔧 Utilizado por desenvolvedores ABAP.

---

### `SE10` – Customizing Requests  
Foco em requests de **Customizing**, que armazenam alterações feitas nas configurações do sistema via SPRO. Exemplo:

- Estrutura organizacional;
- Parâmetros de cálculo de impostos;
- Contas contábeis e dados mestres.

> 🔧 Utilizado por consultores funcionais.

---

### `STMS_IMPORT` – Importação Direta  
Permite acessar diretamente a tela de importação de requests no ambiente de destino (ex: QAS ou PRD). Aqui é possível:

- Visualizar requests prontos para importação;
- Forçar ou agendar importações;
- Acompanhar logs e status pós-importação.

> ✅ Ideal para operações de rotina da equipe BASIS.

---

### `SCC1` – Cópia de Transportes entre Clients  
Usado para **copiar Customizing** de um mandante para outro **dentro do mesmo ambiente SAP**. Muito útil para:

- Testes funcionais;
- Validação de parâmetros antes do transporte para QAS/PRD;
- Replicação de configurações.

> ⚠️ Só permite copiar requests já liberados (`released`).

---

### `TP` – Ferramenta Técnica via Linha de Comando  
Comando executado diretamente no sistema operacional para controlar o processo de transporte. Possibilita:

- Forçar a importação de TRs;
- Validar a integridade dos arquivos;
- Diagnosticar falhas no transporte;
- Executar logs avançados.

> 🔐 Requer acesso ao host SAP e conhecimentos técnicos.

---

### `OS01` – Caminhos Técnicos  
Permite verificar e testar os caminhos físicos onde os arquivos de transporte são armazenados (ex: `/usr/sap/trans`). Verifica:

- Permissões de diretório;
- Conectividade entre ambientes;
- Se os arquivos `.cofiles` e `.data` estão corretamente disponíveis.

---

## 🔄 Etapas Comuns no Transporte

1. **Criação do Transport Request** (`SE09` ou `SE10`)
   - Criado automaticamente ou manualmente ao salvar mudanças técnicas ou funcionais.
   - Objetos ou parâmetros são atribuídos ao request.

2. **Liberação do Request (Release)**
   - Subtasks devem ser liberadas antes do TR principal.
   - Após a liberação, o request fica disponível para importação.

3. **Importação no Ambiente de Destino**
   - Através do `STMS` ou `STMS_IMPORT`, seleciona-se o TR e executa-se a importação.
   - Logs são gerados automaticamente para validação.

4. **Validação Funcional ou Técnica**
   - Após a importação, o conteúdo deve ser testado.
   - Se falhar, deve-se revisar logs e eventualmente reimportar ou corrigir objetos.

---

## ✅ Boas Práticas

- Sempre utilize descrições claras nos TRs (quem, o quê, por quê).
- Não transporte para produção diretamente sem homologação.
- Libere subtasks antes de liberar o request principal.
- Use `SCC1` para testes internos entre mandantes.
- Documente todos os transportes, especialmente os que impactam processos críticos.
- Faça backup e snapshot do ambiente antes de grandes transportes.

---
