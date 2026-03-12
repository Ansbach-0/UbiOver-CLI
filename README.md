# 🤖 UbiOver CLI

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&duration=4000&pause=1000&color=7B2CBF&center=true&vCenter=true&width=600&lines=Gerenciamento+Automatizado+de+Contas;Interface+Híbrida+CLI+%2B+Web+UI;Segurança+com+HWID+%26+Supabase;Automação+com+Pyppeteer" alt="Typing SVG" />
</div>

<div align="center">
  
  ![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
  ![Rich](https://img.shields.io/badge/Rich-CLI-97266D?style=for-the-badge&logo=python&logoColor=white)
  ![PyWebView](https://img.shields.io/badge/pywebview-GUI-8A2BE2?style=for-the-badge&logo=python&logoColor=white)
  ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
  ![Pyppeteer](https://img.shields.io/badge/Pyppeteer-40B5A4?style=for-the-badge&logo=puppeteer&logoColor=white)
  ![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
  
</div>

---

## 🎬 Demonstração em Ação

<div align="center">
  <em>A interface cyberpunk do UbiOver CLI, construída com Rich.</em>
  <br><br>
  <img src="https://github.com/Ansbach-0/UbiOver-CLI/raw/main/ubiover_menu_final.gif" alt="Demonstração do UbiOver CLI" width="800px" />
</div>

---

## 📋 Sobre o Projeto

**UbiOver CLI** é uma poderosa aplicação de console (CLI) com uma **interface web integrada** para automatizar o gerenciamento de contas e o envio de créditos R6. Construído com uma stack de tecnologias modernas:

- **Rich** - Interface interativa e visualmente rica no terminal
- **pywebview** - GUI renderizada com HTML/CSS/JS para seleção visual de itens  
- **Supabase** - Backend robusto para banco de dados e autenticação segura
- **Pyppeteer** - Automação e web scraping avançado

A segurança é um pilar central, com um sistema de login que valida a identidade do usuário através de **HWID (Hardware ID)**, garantindo que o acesso seja restrito a dispositivos autorizados.

---

## ✨ Funcionalidades Principais

<table>
<tr>
<td width="50%">

### 🔐 Segurança & Autenticação
- **Login com Supabase** e verificação de HWID
- **Validação de dispositivos** autorizados
- **Sessões seguras** com tokens criptografados

### 🎮 Automação Inteligente
- **Pyppeteer** para automação web robusta
- **Multithread** para operações não-bloqueantes
- **Gerenciamento de sessões** persistente

</td>
<td width="50%">

### 💼 Gerenciamento CRUD
- **Criar, visualizar, editar e excluir** contas
- **Contas mestras** (origem) e **comuns** (destino)
- **Sincronização automática** com banco de dados

### 🖥️ Interface Híbrida
- **CLI rápido** com Rich para navegação
- **GUI intuitiva** com pywebview para seleções
- **Experiência de usuário** otimizada

</td>
</tr>
</table>

---

## 🔄 Fluxo de Funcionamento

O fluxo de operação foi projetado para ser intuitivo e direto, guiando o usuário em cada etapa do processo.

```mermaid
graph TB
    A[🚀 Início] --> B[🔐 Login Seguro com HWID]
    B --> C{📋 MENU PRINCIPAL}
    
    C --> D[➕ Adicionar Conta]
    D --> E{Mestra ou Comum?}
    E --> C
    
    C --> F[🛒 Enviar Créditos]
    F --> G[🖼️ Escolher Item<br/>Janela pywebview]
    G --> H[💸 Definir Limite de Gastos]
    H --> I[🚀 Iniciar Envio Automatizado]
    I --> J[📊 Atualizar Créditos no BD]
    J --> C
    
    C --> K[📊 Visualizar Contas]
    C --> L[⚙️ Configurações]
    C --> M[🚪 Sair]
    
    style A fill:#7B2CBF,stroke:#fff,stroke-width:2px,color:#fff
    style C fill:#97266D,stroke:#fff,stroke-width:2px,color:#fff
    style I fill:#40B5A4,stroke:#fff,stroke-width:2px,color:#fff
```

### Passo a Passo Detalhado:

1. **🔐 Autenticação:** Login validado pelo Supabase com verificação HWID
2. **📋 Menu Principal:** Interface centralizada para todas as operações
3. **➕ Gerenciamento:** Adicionar contas mestras (origem) ou comuns (destino)
4. **🛒 Seleção:** Interface web para escolha visual de itens
5. **💸 Configuração:** Definir limites de gastos e parâmetros
6. **🤖 Automação:** Processo automatizado em thread separada
7. **📊 Atualização:** Sincronização automática dos saldos no banco
8. **✅ Finalização:** Relatório de sucesso e retorno ao menu

---

## 🏗️ Arquitetura do Sistema

O sistema integra CLI e GUI para uma experiência completa e eficiente.

```mermaid
graph TD
    subgraph "🖥️ Interface do Usuário"
        A[👤 Usuário] --> B[💻 CLI com Rich]
        B -.-> C[🖼️ GUI Web com pywebview]
        C -.-> B
    end

    subgraph "🔐 Camada de Segurança"
        B --> D[🛡️ Sistema de Autenticação]
        D --> E[🔑 Validação HWID]
        D --> F[☁️ Supabase Auth]
    end

    subgraph "⚙️ Core de Automação"
        B --> G[🧵 Gerenciador Multithread]
        G --> H[🤖 Scraper Pyppeteer]
        H --> I[📄 Gerenciador de Sessões]
        H --> J[🌐 Interação Web]
    end

    subgraph "🗄️ Camada de Dados"
        B --> K[📊 CRUD Manager]
        K <--> L[☁️ Supabase Database]
        I <--> M[📁 sessions.json]
    end

    style A fill:#7B2CBF,stroke:#fff,stroke-width:2px,color:#fff
    style D fill:#97266D,stroke:#fff,stroke-width:2px,color:#fff
    style G fill:#40B5A4,stroke:#fff,stroke-width:2px,color:#fff
    style L fill:#3ECF8E,stroke:#fff,stroke-width:2px,color:#fff
```

---

## 📦 Estrutura do Projeto

```
📁 UbiOver-CLI/
├── 🐍 main.py                 # Ponto de entrada da aplicação
├── 📁 core/
│   ├── 🔐 auth.py             # Sistema de autenticação (Supabase + HWID)
│   ├── 🤖 scraper.py          # Engine de automação (Pyppeteer)
│   └── 📊 manager.py          # Gerenciador CRUD de contas
├── 📁 ui/
│   ├── 🎨 components.py       # Componentes UI reutilizáveis
│   └── 🖥️ screens.py          # Telas da aplicação
├── 📁 webview/
│   ├── 🌐 index.html          # Interface de seleção de itens
│   ├── 🎨 style.css           # Estilos modernos da GUI
│   └── ⚡ script.js           # Lógica de interação JavaScript
├── 🗄️ database.py            # Conexão e operações Supabase
├── 📁 sessions/               # Armazenamento de sessões (.json)
├── 📋 requirements.txt        # Dependências Python
└── 📖 README.md              # Esta documentação
```

---

## ⚡ Instalação e Configuração

### Pré-requisitos

- **Python 3.10+**
- **Git**
- **Conta Supabase** (para backend)

### Instalação Rápida

```bash
# 1. Clone o repositório
git clone https://github.com/Ansbach-0/UbiOver-CLI.git
cd UbiOver-CLI

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Configure as variáveis de ambiente
cp .env.example .env
# Edite o arquivo .env com suas credenciais do Supabase

# 4. Execute a aplicação
python main.py
```

### Configuração do Ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
SUPABASE_URL=sua_url_do_supabase
SUPABASE_KEY=sua_chave_do_supabase
DEBUG=False
```

---

## 🚀 Como Usar

### Primeiro Acesso

1. **Execute** `python main.py`
2. **Realize o login** com suas credenciais
3. **Aguarde** a validação do HWID
4. **Acesse** o menu principal

### Adicionando Contas

1. No menu principal, selecione **"Adicionar Conta"**
2. Escolha o tipo: **Mestra** (origem) ou **Comum** (destino)
3. Insira as credenciais da conta
4. Confirme a adição

### Enviando Créditos

1. Selecione **"Enviar Créditos"**
2. Escolha a **conta mestra** (origem)
3. Escolha a **conta comum** (destino)
4. Na janela web, **selecione o item** desejado
5. Defina o **limite de gastos**
6. **Inicie** o processo automatizado

---

## 🛠️ Tecnologias Utilizadas

<div align="center">

| Tecnologia | Versão | Função |
|:----------:|:------:|:-------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) | 3.10+ | Linguagem principal |
| ![Rich](https://img.shields.io/badge/Rich-97266D?style=flat-square&logo=python&logoColor=white) | 13.0+ | Interface CLI avançada |
| ![PyWebView](https://img.shields.io/badge/PyWebView-8A2BE2?style=flat-square&logo=python&logoColor=white) | 4.0+ | GUI híbrida |
| ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white) | - | Backend e autenticação |
| ![Pyppeteer](https://img.shields.io/badge/Pyppeteer-40B5A4?style=flat-square&logo=puppeteer&logoColor=white) | 1.0+ | Automação web |

</div>

---

## 🤝 Contribuindo

Contribuições são sempre bem-vindas! Siga estes passos:

1. **Fork** o projeto
2. **Crie** sua feature branch (`git checkout -b feature/NovaFuncionalidade`)
3. **Commit** suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. **Push** para a branch (`git push origin feature/NovaFuncionalidade`)
5. **Abra** um Pull Request

### Diretrizes para Contribuição

- Mantenha o código limpo e bem documentado
- Siga o padrão PEP 8 para Python
- Adicione testes para novas funcionalidades
- Atualize a documentação quando necessário

---

## 📄 Licença

Distribuído sob a **Licença MIT**. Veja `LICENSE` para mais informações.

```
MIT License - Livre para uso comercial e pessoal
Copyright (c) 2024 Vinícius Ansbach Costa
```

---

## 👨‍💻 Desenvolvedores

<div align="center">
  <img src="https://github.com/Ansbach-0.png" width="100px" style="border-radius: 50%;" alt="Vinícius Ansbach"/>
  <br><br>
  
  **Vinícius Ansbach Costa**
  
  *Desenvolvedor Full Stack & Automation Engineer*
  
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/vinicius-ansbach)
  [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ansbach-0)
  [![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ansbach.vinicius@gmail.com)
  
  <br><br>
  
  <img src="https://github.com/AndreRachid-rgb.png" width="100px" style="border-radius: 50%;" alt="André Rachid"/>
  <br><br>
  
  **André Rachid**
  
  *Desenvolvedor Full Stack*
  
  [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AndreRachid-rgb)
  
</div>

---

## 💬 Suporte

Encontrou um bug ou tem uma sugestão? 

- 🐛 **Issues:** [GitHub Issues](https://github.com/Ansbach-0/UbiOver-CLI/issues)
- 💬 **Discussões:** [GitHub Discussions](https://github.com/Ansbach-0/UbiOver-CLI/discussions)
- 📧 **Email:** ansbach.vinicius@gmail.com

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12&height=120&section=footer&animation=fadeIn" />
  
  **⭐ Se este projeto foi útil para você, considere dar uma estrela!**
  
  ![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=Ansbach-0.UbiOver-CLI)
  
</div>
