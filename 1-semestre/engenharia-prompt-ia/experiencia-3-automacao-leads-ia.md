# Experiência Prática 3 — Automação de Triagem de Leads com IA

Disciplina: Engenharia de Prompt e Aplicações em IA — 1º semestre

## Objetivo

Projetar um fluxo de automação que utiliza IA para qualificar
automaticamente leads recebidos por formulário, reduzindo o tempo de
resposta da equipe de vendas.

## Diagrama do workflow

![Diagrama do workflow de automação](diagramas/diagrama-workflow-leads.png)

> "Este fluxo automatiza a triagem de leads utilizando IA, reduzindo
> tempo de resposta e aumentando eficiência da equipe de vendas."

## Configuração das etapas

### 1. Gatilho (Captura do Lead)
**Ferramenta:** Webhook (Formulário Web)
O fluxo inicia quando o usuário preenche o formulário no site. Os dados
capturados (nome, email e mensagem) são enviados automaticamente via
webhook.

### 2. Webhook
Atua como intermediário, recebendo os dados do formulário e encaminhando
para o sistema de automação — garantindo envio automático e integração
entre sistemas.

### 3. Processamento com IA
**Ferramenta:** OpenAI (modelo GPT)
A mensagem do lead é enviada para o modelo de IA, que analisa e interpreta
a intenção, automatizando a análise e eliminando a triagem manual.

### 4. Classificação
Baseado na resposta da IA, o lead é classificado em:
- **Quente** (alta intenção de compra)
- **Morno** (médio interesse)
- **Frio** (baixo interesse)

### 5. Armazenamento
**Ferramenta:** Google Sheets
Os dados do lead e a classificação são registrados automaticamente em
planilha, organizando e centralizando as informações.

### 6. Notificação
**Ferramenta:** E-mail / CRM / Slack
O sistema envia aviso para a equipe de vendas, priorizando leads quentes
— agilizando o contato e aumentando a conversão.

## Prompt de qualificação utilizado

> Atue como um analista de vendas sênior especializado em qualificação de
> leads para uma agência de marketing digital. Você está analisando
> mensagens enviadas por potenciais clientes através de um formulário de
> contato. Seu objetivo é identificar o nível de interesse e intenção de
> compra do lead.
>
> Classifique a mensagem como uma das seguintes opções:
> - **Quente:** demonstra alta intenção de compra, urgência, interesse em
>   contratar ou menciona orçamento/prazo.
> - **Morno:** demonstra interesse, mas sem urgência ou sem detalhes
>   claros sobre contratação.
> - **Frio:** está apenas buscando informações, fazendo perguntas
>   genéricas ou sem intenção clara de contratar.
>
> Analise cuidadosamente o conteúdo da mensagem e determine a
> classificação correta.
>
> Responda no seguinte formato:
> Classificação: [Quente, Morno ou Frio]
> Justificativa: [Explique em uma frase o motivo da classificação]
> Mensagem do Lead: [Mensagem do Lead]

## Por que a IA é o componente central

O que diferencia essa arquitetura de uma automação tradicional baseada em
regras fixas (ex: busca por palavras-chave) é a capacidade do LLM de
interpretar nuance e contexto. A mesma pergunta pode indicar urgência
diferente dependendo de como foi formulada — algo que regras estáticas
não capturam adequadamente.

## Análise de viabilidade

A utilização de ferramentas low-code/no-code torna o desenvolvimento desse
workflow rápido e eficiente, especialmente na integração entre formulários,
IA e armazenamento em planilhas — permitindo que até usuários com pouco
conhecimento em programação consigam criar soluções funcionais em pouco
tempo.

Por outro lado, a principal limitação está na dependência de múltiplas
plataformas e no custo associado ao uso de APIs de inteligência artificial.
Também pode haver dificuldades de manutenção e depuração em casos de erro,
além de limitações para implementar regras mais complexas.

No geral, a solução é viável, eficiente e escalável para pequenas e médias
demandas.

## Conexão com experiência prévia

Esse tipo de automação de triagem e priorização é conceitualmente familiar
à minha experiência em logística — sistemas WMS fazem algo análogo:
priorizam pedidos com base em regras e urgência, ao invés de processar
tudo na ordem de chegada. A lógica de "classificar para priorizar
atendimento" é a mesma, mudando apenas o domínio de aplicação.

---

[← Voltar para a pasta principal](README.md)
