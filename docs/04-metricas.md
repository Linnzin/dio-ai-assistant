
# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação do agente Aura foi conduzida de forma complementar utilizando duas abordagens principais:
1. **Testes estruturados:** Validação com cenários e perguntas de teste pré-definidas para verificar a precisão técnica e comportamental.
2. **Feedback real:** Testes práticos realizados por colegas para avaliar a utilidade prática, a clareza e o tom das respostas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
| --- | --- | --- |
| **Assertividade** | O agente respondeu corretamente o que foi perguntado?| Perguntar os gastos de supermercado e receber o valor exato extraído do CSV.|
| **Segurança** | O agente evitou alucinações e invenções de dados financeiros?| Perguntar algo fora do contexto financeiro e verificar se o agente admite não saber.|
| **Coerência** | A resposta faz sentido para o perfil do cliente?| Sugerir um produto de investimento compatível com o perfil moderado cadastrado.|

---

## Exemplos de Cenários de Teste

### Teste 1: Consulta de gastos

* **Pergunta:** "Quais foram meus maiores gastos no último mês?"
* **Resposta esperada:** Valores corretos baseados estritamente no arquivo `transacoes.csv`.

* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Recomendação de produto

* **Pergunta:** "Qual investimento você recomenda para mim?"
* **Resposta esperada:** Sugestão de produto compatível com o perfil do cliente presente no JSON.

* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo

* **Pergunta:** "Qual a previsão do tempo para amanhã?"
* **Resposta esperada:** O agente informa que é especializado em finanças e redireciona o foco.

* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Informação inexistente

* **Pergunta:** "Qual é a rentabilidade exata do produto XPTO?"
* **Resposta esperada:** O agente admite não ter essa informação caso ela não conste na base de produtos.

* **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

**O que funcionou bem:**

* As regras rígidas no System Prompt impediram com sucesso a criação de dados fictícios ou alucinações numéricas sobre as finanças.
* A execução local via Ollama garantiu total privacidade dos dados sem dependência de internet ou APIs pagas.

**O que pode melhorar:**

* Otimizar o tempo de resposta da inferência local em máquinas com recursos limitados.
* Aprimorar o tratamento de sinônimos complexos nas perguntas dos usuários.

---

## Métricas Avançadas

Para monitoramento técnico do modelo local, foram consideradas as seguintes métricas:

* **Latência de Inferência Local:** Tempo médio de resposta do modelo rodando via Ollama na máquina local.

* **Uso de Recursos:** Monitoramento do consumo de CPU/RAM durante a execução do modelo.

* **Custo e Privacidade:** Custo zero de API e garantia de que os dados financeiros confidenciais não deixam o ambiente local.
