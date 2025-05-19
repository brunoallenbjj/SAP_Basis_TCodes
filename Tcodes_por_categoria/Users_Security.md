## 👤 Usuários e Segurança

Nesta seção estão as transações essenciais para o gerenciamento de **usuários, perfis, papéis e autorizações no SAP**. São utilizadas por administradores de segurança, BASIS e auditores internos para garantir que os acessos ao sistema sejam controlados de forma adequada e conforme as políticas da empresa.

| Transação                                                                                                                                                                  | O que pode ser feito                       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `SU01`                                                                                                                                                                     | **Manutenção de Usuário SAP**              |
| Permite criar, modificar, bloquear, desbloquear e excluir usuários. É possível configurar dados pessoais, perfis, papéis, parâmetros, grupos e dados específicos de logon. |                                            |
| Exemplo: atribuir a um usuário o papel `ZSD_VENDAS` ou redefinir sua senha.                                                                                                |                                            |
| `SU53`                                                                                                                                                                     | **Análise de Autorização Negada**          |
| Usada quando o usuário recebe uma mensagem de “Acesso negado”. Essa transação mostra **quais objetos de autorização** foram verificados e qual causou a negativa.          |                                            |
| Ideal para troubleshooting rápido com a equipe de segurança.                                                                                                               |                                            |
| `PFCG`                                                                                                                                                                     | **Criação e Manutenção de Papéis (Roles)** |
| É a principal transação para montar a estrutura de segurança baseada em papéis. Nela você pode:                                                                            |                                            |

* Criar papéis com menus, transações e autorizações
* Gerar perfis automaticamente
* Atribuir papéis a usuários (diretamente ou via SU01)
* Organizar papéis técnicos e compostos. |
  \| `SUIM` | **Relatórios e Análises de Segurança**
  Conhecida como “SAP User Information System”, permite gerar relatórios como:
* Quais usuários têm determinado papel
* Quais transações estão contidas em um perfil
* Históricos de acesso
* Relatórios por objeto de autorização
  É muito usada em auditorias e revisões de acesso. |
  \| `SU24` | **Manutenção das Verificações de Autorização**
  Define **quais objetos de autorização são propostos automaticamente** ao incluir transações em papéis pela PFCG.
  Serve como base para as regras do sistema de segurança, reduzindo a manutenção manual de objetos.
  É especialmente relevante no desenvolvimento de programas próprios (Z\*). |
  \| `ST01` | **System Trace (Rastreamento de Autorizações)**
  Permite executar um rastreio técnico das autorizações utilizadas por um usuário ao executar transações ou funções.
  Ajuda a identificar os objetos exatos que estão sendo verificados e se estão sendo negados ou concedidos.
  Ferramenta poderosa para análises profundas de problemas de acesso. |

---

### 🛡️ Dicas de Boas Práticas

* **Nunca atribua perfis manualmente a usuários via SU01** — sempre use papéis via `PFCG`.
* Utilize a transação `SUIM` regularmente para **revisar acessos críticos**.
* Após alterações em papéis, valide os acessos com `SU53` e `ST01` no ambiente de testes.
* Documente exceções e utilize `SU24` para garantir consistência nos objetos de autorização.
