# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

Os dados mockados originais foram mantidos em sua estrutura padrão para garantir a compatibilidade com os scripts de leitura da aplicação. Não houve necessidade de expansão externa, pois os arquivos fornecidos já contêm amostras representativas suficientes de transações, histórico de chamados e perfis de clientes.

---

## Estratégia de Integração

### Como os dados são carregados?

Os arquivos CSV (`transacoes.csv`, `historico_atendimento.csv`) são carregados utilizando a biblioteca `pandas` do Python, enquanto os arquivos JSON (`perfil_investidor.json`, `produtos_financeiros.json`) são carregados através do módulo nativo `json`.

### Como os dados são usados no prompt?

Os dados estruturados são lidos no início da execução da aplicação, convertidos em resumos textuais formatados e injetados dinamicamente no contexto do System Prompt da LLM (ou passados como contexto complementar a cada nova mensagem do usuário) para garantir que o modelo responda com base estrita nas informações do cliente.

---

## Exemplo de Contexto Montado

```text
=== PERFIL DO CLIENTE ===
- Nome: Ana Souza
- Perfil de Risco: Moderado
- Tolerância à Volatilidade: Média
- Patrimônio Alocado: R$ 25.000,00

=== ÚLTIMAS TRANSAÇÕES ===
- 15/05/2026 | Supermercado Extra | R$ -350,00 | Débito
- 18/05/2026 | Posto Shell | R$ -180,00 | Crédito
- 20/05/2026 | Salário Empresa X | R$ +6.500,00 | Pix Recebido

=== PRODUTOS DISPONÍVEIS (Exemplo) ===
- Fundo Renda Fixa IPCA+ (Risco Baixo)
- Fundo Multimercado Balanceado (Risco Moderado)

```
