# 📑 Relatório de Atendimento: Simulação de Incidente N1 (Hardware)

**Analista responsável:** Michael Hernandes Rodrigues  
**Contexto:** Estudo de Caso Prático / Cenário Simulado de Laboratório  
**Classificação do Ticket:** Indisponibilidade de Ativo de Entrada (Teclado)  
**Framework de Processos:** Alinhado com Gerenciamento de Incidentes (ITIL / GRC)  

---

## 🔍 1. Descrição do Cenário Mapeado (Sintomas)
Em um cenário de simulação prática de atendimento, mapeou-se a impossibilidade de autenticação de um operador em sua estação de trabalho. O usuário fictício alegou que "não conseguia digitar a senha nem o login no computador" e que "ao clicar no teclado, nada aparecia na tela". O bloqueio simulado impedia o início das atividades operacionais corporativas, gerando uma indisponibilidade local de acesso.

---

## 🛠️ 2. Diagnóstico Técnico de Laboratório (Troubleshooting)
Para solucionar o incidente simulado, o processo estruturado seguiu o método de eliminação lógica de falhas:

1. **Análise de Software (Sistemas):** Verificação visual se a tela de login estava travada ou congelada. O mouse respondia normalmente, eliminando a hipótese de travamento total do Sistema Operacional (Windows/Linux).
2. **Análise de Hardware (Física):** Inspeção visual e física dos periféricos conectados à CPU. 
3. **Identificação da Causa Raiz:** Durante o mapeamento simulado dos cabos, identificou-se que o conector USB do teclado estava frouxo e parcialmente desconectado na parte traseira do gabinete. 

**Fato Gerador Simulado:** Constatou-se no cenário que o incidente ocorreu de forma acidental durante a rotina de limpeza física do ambiente, onde o cabo foi esbarrado e desconectado da porta USB.

---

## ✅ 3. Solução Aplicada e Encerramento do Cenário
* **Ação Corretiva:** Desconexão total e reinserção firme do cabo USB do teclado em uma porta funcional da placa-mãe.
* **Validação:** Simulação do teste de digitação na tela de autenticação. Os caracteres foram processados instantaneamente, restabelecendo o fluxo normal de login.
* **Resultado:** Sistema operacional e periféricos operando com 100% de disponibilidade no ambiente de teste.

---

## 🧠 Conexão com GRC e Segurança da Informação (ISO 27001)
A resolução desse laboratório prático fundamenta-se nos seguintes aprendizados analíticos de Governança e Riscos:

* **Segurança Física (ISO/IEC 27001 - Controle A.7):** Evidencia a importância da proteção dos ativos de TI contra interferências físicas ou acidentais, servindo como modelo de conscientização de riscos operacionais.
* **Treinamento e Postura de Atendimento:** Desenvolve a capacidade de comunicação técnica assertiva e empática, isolando problemas metodicamente.
* **Base de Conhecimento:** O registro deste laboratório alimenta a base de conhecimento simulada de N1, demonstrando maturidade na documentação de incidentes.

---
[⬅️ Voltar para o Painel de Evolução](./README.md)
