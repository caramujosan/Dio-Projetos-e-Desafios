# Código da Aplicação

## Estrutura Sugerida (projetos mais complexos)

```
src/
├── app.py              # Aplicação principal (Streamlit/Gradio)
├── agente.py           # Lógica do agente
├── config.py           # Configurações (API keys, etc.)
└── requirements.txt    # Dependências
```
---

# Passo a Passo de Execução

## Código Completo

Todo o código-fonte está no arquivo `app.py`.

## Setup do Ollama

```bash
# 1. Baixar Ollama (ollama.com)
# 2. Instalar Ollama
# 3. Baixar um modelo leve
ollama run gpt-oss:20b [https://ollama.com/library/gpt-oss:20b](https://ollama.com/library/gpt-oss:20b)

# 3. Testar se funciona
ollama run gpt-oss:20b "Olá!"
```

## Como Rodar

```bash
# 1. Instalar dependências
pip install -r requirements.txt

# 2. Garantir que Ollama está rodando
ollama serve

# 3. Rodar o app
streamlit run .\src\app.py
```

## Evidência de Execução

<img width="1920" height="1107" alt="image" src="https://github.com/user-attachments/assets/" />
