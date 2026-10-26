# 🛠️ Projeto Prático: Estruturação de Help Desk e Gestão de Incidentes Operacionais (N1)

Este projeto prático simula a estruturação do setor de Help Desk e Suporte N1 para a empresa fictícia **TechCorp**. O objetivo é demonstrar a aplicação prática de fluxos operacionais, catálogos de serviços, Acordos de Nível de Serviço (SLA) e manutenções de segurança na ponta (Endpoint Security), alinhando a operação técnica aos controles de conformidade da **ISO/IEC 27001**.

---

## 🎯 Cenário do Projeto
A **TechCorp** contava com um suporte reativo e sem padronização, gerando atrasos em correções críticas e falta de rastreabilidade de acessos. Como Analista de Suporte N1, estruturei um modelo de operação baseado nas melhores práticas de gerenciamento de serviços de TI e segurança da informação.

---

## 🗂️ 1. Catálogo de Serviços e Matriz de SLA (Service Level Agreement)

Para organizar as demandas de entrada, os chamados foram categorizados com níveis de prioridade e tempos máximos de atendimento/resolução:

| Categoria do Chamado | Impacto Organizacional | Prioridade | SLA de Atendimento | SLA de Solução |
| :--- | :--- | :--- | :--- | :--- |
| **Incidente de Segurança** (Suspeita de malware/phishing) | Alto (Risco de Vazamento) | **Crítica** | 15 minutos | 1 hora |
| **Bloqueio de Usuário / Senha** (Trabalhador inoperante) | Médio (Parada de Produtividade) | **Alta** | 30 minutos | 2 hours |
| **Falha de Software Corporativo** (Instalação/Erros) | Baixo (Individual) | **Média** | 2 horas | 8 horas |
| **Configuração de Novo Hardware** (Setup de máquina) | Baixo (Planejado) | **Baixa** | 4 horas | 24 horas |

---

## 📑 2. Base de Conhecimento: Procedimentos Operacionais Padrão (POP)

Abaixo estão os guias práticos utilizados pela equipe de N1 para garantir a conformidade com as políticas de controle de acesso (ISO/IEC 27001):

### POP 01: Procedimento de Reset de Senha Seguro
1. **Identificação Prévia:** Nunca resetar uma credencial sem validar a identidade do colaborador (via chamada de vídeo ou confirmação de dados com o RH).
2. **Geração de Senha Temporária:** Utilizar o sistema integrado para gerar uma senha forte provisória.
3. **Exigência de Troca:** Marcar a opção *"O usuário deve alterar a senha no próximo logon"* no Active Directory.
4. **Encerramento:** Registrar o ID do chamado e o método de validação de identidade utilizado.

### POP 02: Isolamento de Endpoint em Suspeita de Infecção (Malware)
1. **Isolamento de Rede:** Instruir o usuário a desconectar o cabo de rede e desligar o Wi-Fi do dispositivo imediatamente.
2. **Coleta de Evidências:** Registrar o horário do sintoma e coletar prints de alertas do antivírus corporativo (se houver).
3. **Revogação Temporária:** Suspender preventivamente as sessões ativas do usuário nos sistemas em nuvem através do painel de administração.
4. **Escalação:** Abrir chamado de prioridade **Crítica** e escalar para o time de Segurança (N2/SOC).

---

## 💻 3. Scripts Automações Práticas para Auditoria de Ponta

Para auxiliar na auditoria operacional diária, foram desenvolvidos scripts utilitários focados em segurança local:

### Script A: Auditoria de Usuários no Grupo de Administradores Locais (Windows)
Este comando lista todos os usuários que possuem privilégios administrativos na máquina local, garantindo que o princípio do menor privilégio (Least Privilege) seja auditado.

```cmd
:: Executar no Prompt de Comando (CMD) como Administrador
net localgroup administradores > relatorio_admins.txt
type relatorio_admins.txt
```

### Script B: Verificação de Compartilhamentos de Rede Ativos
Identifica pastas locais que estão sendo compartilhadas na rede interna sem as devidas permissões corporativas.

```powershell
# Executar no PowerShell como Administrador
Get-SmbShare | Where-Object {(\(_.Name -notlike "*\)")} | Select-Object Name, Path, Description
```

---

## 🛡️ Conexão com GRC & ISO/IEC 27001

A existência e execução correta deste projeto de Help Desk apoia diretamente os seguintes controles do Anexo A da **ISO/IEC 27001:2022**:
*   **Controle A.5.25 (Gestão de Incidentes de Segurança da Informação):** O SLA agressivo para tratamento de incidentes de segurança garante a rápida contenção na ponta.
*   **Controle A.8.2 (Privilégios de Acesso):** Os scripts de auditoria impedem que usuários comuns mantenham privilégios elevados indevidamente nas estações de trabalho.

---

🔙 [Voltar para o Painel de Evolução](../)
