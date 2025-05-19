# 📘 Guia Interativo de Transações SAP (TCODES)

Este repositório contém uma referência interativa e bem organizada para os principais Códigos de Transação (TCODES) do SAP. Os códigos estão agrupados por função para facilitar a navegação, monitoramento do sistema, desenvolvimento e mais. Agora com descrições do que pode ser feito em cada uma delas.

---

## 🔀 Navegação e Gerenciamento de Sessões

| TCode     | Descrição                                                               | O que pode ser feito |
|-----------|-------------------------------------------------------------------------|-----------------------|
| `/n`      | Cancela a transação atual.                                              | Sai da tela atual e retorna à inicial. |
| `/nXXXX`  | Acessa diretamente a transação XXXX a partir de outra transação.       | Navega diretamente para outra transação. |
| `/o`      | Exibe a visão geral das suas sessões.                                   | Visualiza todas as sessões abertas. |
| `/oXXXX`  | Abre a transação XXXX em uma nova sessão.                              | Inicia a transação em uma nova aba. |
| `/nend`   | Encerra a sessão atual (com confirmação).                              | Fecha o SAP com aviso. |
| `/nex`    | Encerra a sessão atual (sem confirmação).                              | Fecha o SAP imediatamente. |
| `/i`      | Encerra a sessão atual imediatamente.                                  | Fecha apenas a aba atual. |
| `SAP1`    | Ajuda geral do SAP.                                                    | Acessa uma central de ajuda do sistema. |
| `S000`    | Tela inicial padrão.                                                   | Volta para a tela inicial. |

---

## 🛠️ Monitoramento e Administração do Sistema

| TCode   | Descrição                                           | O que pode ser feito |
|---------|-----------------------------------------------------|-----------------------|
| SM50    | Processos de trabalho da instância atual.          | Monitora e finaliza work processes. |
| SM66    | Processos em toda a paisagem SAP.                  | Verifica consumo de recursos por instância. |
| SM04    | Usuários conectados.                               | Desconecta usuários, analisa sessões. |
| SM12    | Entradas de bloqueio em tabelas.                   | Libera registros travados manualmente. |
| SM13    | Registros de atualização.                          | Analisa falhas de atualização. |
| SM21    | Logs do sistema.                                   | Investiga erros e mensagens do sistema. |
| SM37    | Jobs de background.                                | Verifica, reexecuta, cancela jobs. |
| SM59    | Conexões RFC.                                      | Testa e configura conexões externas. |
| SMQ1    | Filas de saída.                                    | Reprocessa ou limpa mensagens pendentes. |
| SMQ2    | Filas de entrada.                                  | Gerencia mensagens recebidas. |
| ST22    | Dumps ABAP.                                        | Diagnostica erros de execução. |
| ST06    | Utilização de hardware.                            | Verifica memória, CPU, disco. |
| SPAD    | Impressoras SAP.                                   | Cria, testa e atribui dispositivos de impressão. |
| SLICENSE| Chaves de licença SAP.                             | Atualiza ou visualiza validade e número de licenças. |
| SPAM    | Pacotes de suporte.                                | Aplica updates técnicos no SAP. |
| SAINT   | Add-ons e componentes.                             | Instalações técnicas e upgrades. |
| SMGW    | Gateway SAP.                                       | Monitora conexões externas com o SAP. |
| RZ01    | Tarefas de background.                             | Agendamento automático de jobs. |
| RZ20    | CCMS - Central de alertas.                         | Gera alertas e monitora status do sistema. |
| ST03N   | Análise de performance.                            | Identifica gargalos e cargas de trabalho. |
| ST07    | Estatísticas do cliente.                           | Detalha consumo de licença por cliente. |

---

## 📐 Desenvolvimento e Dicionário de Dados

| TCode | Descrição                                  | O que pode ser feito |
|-------|----------------------------------------------|-----------------------|
| SE11  | Dicionário ABAP.                             | Criação de tabelas, views, domínios, estruturas. |
| SE14  | Administração de banco de dados.             | Reorganização e ajustes em tabelas. |
| SE16  | Navegador de dados.                          | Consulta de dados de tabelas. |
| SE16N | Navegador de dados avançado.                 | Consultas com filtros e exportações de dados. |
| SE38  | Editor ABAP.                                 | Desenvolvimento de programas ABAP. |
| SE80  | Navegador de objetos.                        | Acesso a todos os objetos de desenvolvimento. |
| SE93  | Códigos de transação.                        | Criação e manutenção de transações personalizadas. |
| STMS  | Sistema de transporte.                       | Transporte de objetos entre ambientes. |
| WE02  | Lista de IDocs.                              | Diagnóstico de erros de integração. |
| WE19  | Teste de IDocs.                              | Simulação de IDocs para testes. |
| SE37  | Funções ABAP.                                | Testa e modifica funções, BAPIs. |

---

## 👤 Gestão de Usuários e Segurança

| TCode | Descrição                                   | O que pode ser feito |
|-------|-----------------------------------------------|-----------------------|
| SU01  | Manutenção de usuários.                      | Criar, bloquear, alterar senha e perfis. |
| SU53  | Verifica autorizações.                       | Diagnostica acessos negados. |
| PFCG  | Papéis e autorizações.                       | Criação de perfis de acesso por função. |
| SUIM  | Relatórios de segurança.                     | Análise de acessos, permissões, logs. |
| SU24  | Objetos de autorização por transação.        | Ajusta verificações de segurança. |
| ST01  | Rastreamento de autorizações.                | Captura erros em tempo real. |
| SU10  | Manutenção em massa.                         | Alterações em grupo de usuários. |
| RSUSR200 | Auditoria de usuários.                    | Identifica contas inativas ou problemáticas. |

---

## 🛒 Logística e Transações Operacionais

| TCode | Descrição                                       | O que pode ser feito |
|-------|---------------------------------------------------|-----------------------|
| VA01  | Pedido de venda.                                 | Criação de vendas para clientes. |
| VA03  | Visualização de pedido.                          | Consulta e impressão de pedidos. |
| VL01N | Entrega de mercadoria.                           | Geração de entrega física. |
| VL02N | Alteração de entrega.                            | Ajustes antes do faturamento. |
| VF01  | Faturamento.                                     | Criação de nota fiscal. |
| MM01  | Material.                                        | Cadastro completo de item/material. |
| MM02  | Alteração de material.                           | Modificação de descrição, unidade, etc. |
| MM03  | Visualização de material.                        | Consulta completa de dados do item. |
| ME21N | Pedido de compra.                                | Compra de mercadoria/serviços. |
| ME23N | Visualização de pedido de compra.                | Ver histórico de compras. |
| MB1C  | Entrada inicial de estoque.                      | Registro inicial de materiais. |
| MB51  | Lista de movimentações.                          | Análise de documentos de estoque. |
| FB03  | Documento contábil.                              | Visualiza lançamentos e seus detalhes. |
| F-28  | Recebimento de cliente.                          | Lançamento de recebimento bancário. |
| F-43  | Fatura de fornecedor.                            | Lançamento de contas a pagar. |
| IW31  | Ordem de manutenção.                             | Programação de serviços técnicos. |
| IW32  | Alteração de ordem de manutenção.                | Atualização de status, descrição, recursos. |

---

## ⚙️ Configuração e Customização do Sistema

| TCode | Descrição                                         | O que pode ser feito |
|-------|---------------------------------------------------|-----------------------|
| SPRO  | IMG - Customização do sistema.                    | Acesso ao menu de configuração por módulo. |
| RZ10  | Parâmetros de perfil.                             | Alteração de parâmetros de instância. |
| RZ11  | Parâmetros ativos.                                | Consulta rápida de parâmetros de sistema. |
| ST04  | Banco de dados.                                   | Análise de performance do DB. |
| DB02  | Crescimento do banco de dados.                    | Projeções de espaço, crescimento de tabelas. |
| AL11  | Diretórios do SAP.                                | Acesso aos arquivos do sistema SAP. |
| OSS1  | Portal de suporte SAP.                            | Abertura de chamados com a SAP. |
| SM30  | Visualização de tabelas customizadas.             | Entrada de dados em tabelas Z. |
| SOBJ  | Objetos de transporte.                            | Marcação de objetos para transporte. |
| SCC4  | Configuração de cliente.                          | Define permissões para alterações em clientes. |

---

## 📊 Relatórios e Análises

| TCode | Descrição                                         | O que pode ser feito |
|-------|---------------------------------------------------|-----------------------|
| SQVI  | QuickViewer.                                      | Criação de relatórios sem programação. |
| SQ01  | Infoset Query.                                    | Relatórios por infoset personalizados. |
| SE16N | Dados avançados.                                  | Extração de grandes volumes com filtros. |
| MB51  | Documentos de material.                           | Histórico completo de movimentações. |
| ME2N  | Pedidos de compra.                                | Relatórios por fornecedor, data ou material. |
| ME80FN| Relatório completo de compras.                    | Visão analítica com detalhes de itens. |
| FBL1N | Itens de fornecedor.                              | Análise de contas a pagar. |
| FBL3N | Razão contábil.                                   | Movimentações por conta contábil. |
| FBL5N | Itens de cliente.                                 | Análise de contas a receber. |
| S_ALR_87012357 | Saldos de contas contábeis.              | Relatórios financeiros. |
| S_ALR_87012082 | Comparação de custos planejados/atuais.  | Controle de orçamento. |

---

## 📂 Contribuindo

Sinta-se à vontade para fazer fork do repositório e enviar pull requests com:
- Correções ou atualizações;
- Novos TCODES;
- Prints de tela, diagramas ou explicações adicionais.

---

## 📎 Licença

Este repositório está licenciado sob a Licença MIT.

---

## 🔗 Links Úteis
- [Portal de Ajuda SAP](https://help.sap.com/)
- [Comunidade SAP](https://community.sap.com/)
- [Cursos OpenSAP](https://open.sap.com/)

---

> _Este repositório tem como objetivo ser uma base de conhecimento colaborativa para profissionais SAP. Colabore com melhorias!_
