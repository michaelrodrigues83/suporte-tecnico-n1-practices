# 📑 Relatório de Atendimento: Simulação de Incidente N1 (Sistemas Operacionais)

**Analista responsável:** Michael Hernandes Rodrigues  
**Contexto:** Estudo de Caso Prático / Cenário Simulado de Laboratório (Bloco 2)  
**Classificação do Ticket:** Gerenciamento de Identidades e Acessos (IAM) / Permissões de Arquivos  
**Framework de Processos:** Alinhado com as diretrizes de Controle de Acesso Baseado em Funções (RBAC)  

---

## 🔍 1. Descrição do Cenário Mapeado (Sintomas)
Em um cenário de simulação de suporte administrativo, um novo colaborador do departamento Financeiro reportou que, após o primeiro login em sua estação de trabalho (ambiente Windows/Linux simulado), não conseguia acessar a pasta de relatórios compartilhados da equipe. O sistema exibia a mensagem de erro clássica: *"Acesso Negado. Você não tem permissão para acessar este recurso"*.

---

## 🛠️ 2. Diagnóstico Técnico de Laboratório (Troubleshooting)
Para solucionar essa indisponibilidade de privilégios, o fluxo de verificação lógica de contas e grupos seguiu os seguintes passos de administração de sistemas:

1. **Verificação de Identidade (IAM):** Validação no diretório de usuários se a conta do novo colaborador foi criada dentro da árvore correta e associada ao departamento correspondente.
2. **Análise de Herança de Permissões:** Diagnóstico das listas de controle de acesso (ACL) da pasta compartilhada para mapear se os privilégios estavam bloqueados ou desalinhados.
3. **Identificação da Causa Raiz:** Constatou-se no laboratório que a conta de usuário foi criada com sucesso, porém o analista de RH esqueceu de incluir o perfil do colaborador no grupo de segurança global corporativo `GG_Financeiro`. Como a pasta só concede acesso a membros desse grupo, o usuário ficou sem permissão de leitura.

---

## ✅ 3. Solução Aplicada e Encerramento do Cenário
* **Ação Corretiva:** Inclusão manual da conta do colaborador dentro do grupo de segurança `GG_Financeiro` através do console de administração do sistema.
* **Aplicação do Privilégio Mínimo:** Concessão executada com extrema cautela, assegurando que o nível de acesso liberado fosse estritamente o suficiente e limitado à parte de trabalho e escopo operacional dele. 
* **Refinamento de Permissões (RBAC):** Configuração de privilégios na pasta garantindo permissão de **Leitura e Escrita** para seus arquivos de rotina, mas aplicando restrição total (**Sem Acesso**) a diretórios confidenciais da diretoria ou de outros setores.
* **Validação:** Simulação de atualização de políticas de segurança na estação de trabalho do usuário. O acesso à pasta foi liberado instantaneamente, restabelecendo a disponibilidade operativa de forma segura.

---

## 🧠 Conexão com GRC e Segurança da Informação (ISO 27001)
A execução deste laboratório prático do Bloco 2 fundamenta-se nas seguintes premissas de Governança de TI:

* **Princípio do Privilégio Mínimo (ISO/IEC 27001 - Controle A.8.2):** Demonstra a importância prática de garantir que os usuários possuam apenas os acessos estritamente necessários para o desempenho de suas funções profissionais, mitigando riscos de vazamento por excesso de privilégios através de uma postura cautelosa do analista.
* **Gerenciamento de Direitos de Acesso (Controle A.8.3):** Evidencia como a concessão, modificação e revogação de acessos devem seguir um processo estruturado e auditável para evitar "acúmulo de privilégios" ao longo do tempo.
* **Segregação de Funções:** Utilização prática de grupos de segurança (`GG_Financeiro`) para automatizar e auditar a governança de identidades dentro de uma infraestrutura de rede corporativa.

---
[⬅️ Voltar para o Painel de Evolução](./README.md)
