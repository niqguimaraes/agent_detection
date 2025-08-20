# 🔐 STRIDE Threat Model Analyzer

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?logo=fastapi)
![Frontend](https://img.shields.io/badge/Frontend-HTML%2FCSS%2FJS-F7DF1E?logo=javascript)

> Aplicação para modelagem de ameaças baseada em **STRIDE**, com backend em **FastAPI** e front-end em **HTML/CSS/JS**.

---

<details>
<summary><strong>📑 Sumário</strong></summary>

- [Funcionalidades](#-funcionalidades)
- [Como executar](#-como-executar)
- [Estrutura do projeto](#-estrutura-do-projeto)
</details>

---

## ✅ Funcionalidades
- Upload de imagem/diagrama de arquitetura + metadados do sistema
- Geração automática do modelo STRIDE via **Azure OpenAI**
- Sugestões de melhorias para o modelo de ameaças
- Exportação/impressão do grafo gerado

---

## 🧭 Como executar

### 1) Requisitos
- **Python 3.10+**
- **Node.js** *(opcional, apenas para servir o front-end localmente)*
- Acesso e deployment configurado no **Azure OpenAI**

> [!WARNING]
> Sem as variáveis do Azure OpenAI corretamente definidas no `.env`, a geração do STRIDE não funcionará.

---

### 2) Clonar o repositório
```bash
git clone https://github.com/digitalinnovationone/stride-demo.git
cd stride-demo
```

---

### 3) Backend (FastAPI)
```bash
cd module-1/01-introducao-backend
python -m venv .venv
```

#### Ativação
#### Linux/Mac:
```bash
source .venv/bin/activate
```
#### Windows (PowerShell):
```bash
.venv\Scripts\Activate.ps1

pip install -r requirements.txt
```

#### .Env Model
```bash
AZURE_OPENAI_API_KEY=xxxxxx
AZURE_OPENAI_ENDPOINT=https://<seu-endpoint>.openai.azure.com/
AZURE_OPENAI_API_VERSION=xxxx-xx-xx
AZURE_OPENAI_DEPLOYMENT_NAME=<nome-do-deployment>
```

#### Inicie a API
```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8001
```

---

### 4) Front-end
```bash
cd ../02-front-end
```

Abra index.html diretamente no navegador ou execute localmente:
```bash
npx serve .
```
#### ou
```bash
python -m http.server 8080
```

[!NOTE]
O front-end espera o backend em http://localhost:8001

## 🗂 Estrutura do projeto

```bash
📦 stride-demo/
├── 📁 module-1/
│   ├── 📂 01-introducao-backend/   # 🚀 Backend (FastAPI)
│   │   ├── 🐍 main.py              # Código principal da API
│   │   ├── 📜 requirements.txt     # Dependências do backend
│   │   └── 🔑 .env                 # Variáveis de ambiente (criado pelo usuário)
│   │
│   └── 📂 02-front-end/            # 🎨 Frontend
│       └── 🌐 index.html           # Página principal do front-end
│
└── 📘 README.md                    # Documentação do projeto
