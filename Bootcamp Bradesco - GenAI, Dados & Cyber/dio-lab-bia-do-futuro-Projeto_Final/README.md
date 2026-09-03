# :warning: Muquirana - Contador Inteligente
> Agente de IA Generativa de alerta de gastos e gestão financeira de forma simples e personalizada, usando os próprios dados fornecidos do cliente.

## 💡 O Que é o Muquirana?
O Muquirana é um contador pessoal que alerta sobre gastos pessoais e ajuda com gestão financeira. Ele não recomenda tipos de investimentos, apenas faz análise de gastos dos dados financeiros do cliente.

O que o Muquirana faz:
- ✅ Analisa os padrões de gastos do cliente
- ✅ Usa dados do cliente como alerta
- ✅ Responde dúvidas sobre a análise
- ✅ Recomenda cortes de gasto

O que o Muquirana NÃO faz:
- ❌ Não recomenda investimentos gerais ou específicos
- ❌ Não acessa dados bancários sensíveis
- ❌ Não substitui um contador profissional certificado

## :construction_worker: Arquitetura
flowchart TD
    A(Cliente)-->B[Streamlit]
    B-->C[Ollama - LLM Local]
    C-->D{Base de Conhecimento}
    D-->C;
    C-->E[Resposta da análise]
    E-->A

### Stack:
- Interface: Streamlit
- LLM: Ollama (modelo local gpt-oss)
- Dados: JSON/CSV mockados

## 📁 Estrutura do Projeto
```
├── data/                          # Base de conhecimento
│   ├── perfil_investidor.json     # Perfil do cliente
│   ├── transacoes.csv             # Histórico financeiro
│   ├── historico_atendimento.csv  # Interações anteriores
│   └── produtos_financeiros.json  # Produtos para ensino
│
├── docs/                          # Documentação completa
│   ├── 01-documentacao-agente.md  # Caso de uso e persona
│   ├── 02-base-conhecimento.md    # Estratégia de dados
│   ├── 03-prompts.md              # System prompt e exemplos
│   ├── 04-metricas.md             # Avaliação de qualidade
│   └── 05-pitch.md                # Apresentação do projeto
│
└── src/
    └── app.py                     # Aplicação Streamlit
```

## 🚀 Como Executar
### 1. Instalar Ollama
```
# Baixar em: ollama.com
ollama pull gpt-oss
ollama serve
```

### 2. Instalar Dependências
```
pip install streamlit pandas requests
```

### 3. Rodar o Edu
```
streamlit run src/app.py
```

## 🎯 Exemplo de Uso
Pergunta: "Onde estou gastando mais?"
Edu: ""

Pergunta: "Como posso economizar?"
Edu: ""

## 📊 Métricas de Avaliação
|Métrica | Objetivo |
|--------|----------|
| Assertividade | O agente responde o que foi perguntado? |
| Segurança | Evita inventar informações (anti-alucinação)? |
| Coerência | A resposta é adequada ao objetivo de análise de gastos? |

## 🎬 Diferenciais
- Personalização: Usa os dados do próprio cliente nos exemplos
- 100% Local: Roda com Ollama, sem enviar dados para APIs externas
- Consultivo: Foco em analisar gastos, não em vender produtos
- Seguro: Estratégias de anti-alucinação documentadas

## 📝 Documentação Completa
Toda a documentação técnica, estratégias de prompt e casos de teste estão disponíveis na pasta [](docs/).
