# 🤖 Aura - Agente Financeiro Inteligente com IA Generativa

## Sobre o Projeto

O **Aura** é um agente financeiro inteligente e proativo desenvolvido para auxiliar usuários no controle de gastos, análise de transações e planejamento de investimentos. O sistema opera de forma totalmente local, garantindo privacidade e segurança dos dados financeiros sem dependência de internet ou APIs de terceiros.

---

## Estrutura do Repositório

```text
📁 lab-agente-financeiro/
│
├── 📄 README.md
│
├── 📁 data/                          # Dados mockados para o agente
│   ├── historico_atendimento.csv     # Histórico de atendimentos (CSV)
│   ├── perfil_investidor.json        # Perfil do cliente (JSON)
│   ├── produtos_financeiros.json     # Produtos disponíveis (JSON)
│   └── transacoes.csv                # Histórico de transações (CSV)
│
├── 📁 docs/                          # Documentação do projeto
│   ├── 01-documentacao-agente.md     # Caso de uso e arquitetura local
│   ├── 02-base-conhecimento.md       # Estratégia de dados e integração
│   ├── 03-prompts.md                 # System prompt e engenharia de prompts
│   └── 04-metricas.md                # Avaliação de qualidade e métricas locais
│
└── 📁 src/                           # Código da aplicação

```
---

## Documentação

Toda a concepção, regras de segurança anti-alucinação, bases de dados e estratégias de engenharia de prompt estão detalhadas na pasta [`docs/`](docs/).
