# Código da Aplicação

## Estrutura Sugerida (projetos mais complexos)

```text
src/
├── app.py              # Aplicação principal (Streamlit/Gradio)
├── agente.py           # Lógica do agente
├── config.py           # Configurações (API keys, etc.)
└── requirements.txt    # Dependências
```

---

## Estrutura Usada no Projeto

```text
src/
├── app.py              # Aplicação principal (Streamlit/Gradio)
└── requirements.txt    # Dependências
```

---

## Passo a Passo de Execução

### Setup do Ollama

```bash
# 1. Baixar Ollama (ollama.com)
# 2. Instalar Ollama
# 3. Baixar um modelo leve
ollama run gpt-oss:20b

# 4. Testar se funciona
ollama run gpt-oss:20b "Olá!"
```

:llama: [https://ollama.com/](https://ollama.com/)

[https://ollama.com/library/gpt-oss:20b](https://ollama.com/library/gpt-oss:20b)

### Como Rodar

```bash
# 1. Instalar dependências
pip install -r requirements.txt

# 2. Garantir que Ollama está rodando
ollama serve

# 3. Rodar o app
streamlit run .\src\app.py
```

### Evidência de Execução

<img width="1920" height="1107" alt="image" src="https://github.com/caramujosan/Dio-Projetos-e-Desafios/blob/main/Bootcamp%20Bradesco%20-%20GenAI%2C%20Dados%20%26%20Cyber/dio-lab-bia-do-futuro-Projeto_Final/assets/screenshot-streamlit.png" />
