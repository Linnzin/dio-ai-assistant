# Documentação do Agente

## Caso de Uso

### Problema

Muitos clientes bancários enfrentam dificuldades para controlar seus gastos diários, entender seu perfil de investimento real, planejar metas financeiras e analisar o histórico de atendimentos anteriores. Além disso, os canais tradicionais costumam ser reativos e faltam orientações personalizadas e proativas.

### Solução

O agente atua como um consultor financeiro pessoal inteligente que cruza o histórico de transações, o perfil do investidor e o catálogo de produtos financeiros para antecipar alertas de gastos excessivos, sugerir opções de investimento alinhadas ao perfil do cliente e responder dúvidas de forma consultiva e contextualizada.

### Público-Alvo

Clientes de serviços financeiros (bancos digitais ou tradicionais) que buscam otimizar suas finanças pessoais, planejar investimentos e obter suporte rápido e assertivo sem precisar navegar por menus complexos.

---

## Persona e Tom de Voz

### Nome do Agente
Aura (Assistente Única de Respostas e Análises).

### Personalidade

Consultivo, empático, educativo e objetivo. Foca em orientar o cliente de forma clara, ajudando-o a tomar decisões financeiras conscientes.

### Tom de Comunicação

Acessível e profissional. Utiliza uma linguagem clara, descontraída na medida certa, mas séria quando o assunto envolve segurança financeira.

[Sua descrição aqui]

### Exemplos de Linguagem
* Saudação: "Olá! Sou a Aura, sua assistente financeira inteligente. Como posso te ajudar a cuidar do seu dinheiro e planejar seus objetivos hoje?"
* Confirmação: "Entendi perfeitamente! Vou analisar o seu histórico de transações e o seu perfil de investidor para verificar essa informação."
* Erro/Limitação: "Não encontrei essa informação específica nos seus registros atuais, mas posso te orientar sobre as opções disponíveis no nosso catálogo de produtos."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
| --- | --- |
| Interface | Chatbot interativo desenvolvido em Streamlit |
| LLM | Modelo de linguagem avançado via API (ex: Gemini / GPT-4) |
| Base de Conhecimento | Arquivos estruturados (`transacoes.csv`, `perfil_investidor.json`, `produtos_financeiros.json`, `historico_atendimento.csv`)|
| Validação | Camada de restrição de prompt para prevenção de alucinações baseada estritamente nos dados fornecidos |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

* [x] O agente só responde com base nos dados fornecidos nas bases de conhecimento mockadas.
* [x] As respostas incluem referências diretas aos dados do cliente (ex: extratos e perfil de risco).
* [x] Quando não possui a informação, o agente admite explicitamente e redireciona para os canais adequados.
* [x] O agente não faz recomendações de investimento que fujam do perfil de investidor cadastrado.

### Limitações Declaradas

* Não executa transações financeiras reais (como transferências, pagamentos ou investimentos diretos).
* Não inventa taxas de juros, rentabilidades ou produtos que não estejam documentados na base de produtos financeiros.
* Não substitui assessoria jurídica ou contábil formal para casos complexos.
