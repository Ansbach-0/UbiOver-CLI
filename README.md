🤖 UbiOver CLI

<div align="center">
<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&duration=4000&pause=1000&color=7B2CBF&center=true&vCenter=true&width=600&lines=Gerenciamento+Automatizado+de+Contas;Interface+Híbrida+CLI+%2B+Web+UI;Segurança+com+HWID+%26+Supabase;Automação+com+Pyppeteer" alt="Typing SVG" />
</div>

<div align="center">

</div>
🎬 Demonstração em Ação

<div align="center">
<em>A interface cyberpunk do UbiOver CLI, construída com Rich.</em>
<br><br>
<img src="https://github.com/Ansbach-0/UbiOver-CLI/raw/main/ubiover_menu_final.gif" alt="Demonstração do UbiOver CLI" width="800px" />
</div>
📋 Sobre o Projeto

UbiOver CLI é uma poderosa aplicação de console (CLI) com uma interface web integrada para automatizar o gerenciamento de contas e o envio de créditos R6. Construído com uma stack de tecnologias modernas, o projeto utiliza:

    Rich para uma interface interativa e visualmente rica no terminal.

    pywebview para renderizar uma GUI com HTML/CSS/JS, permitindo a seleção visual de itens.

    Supabase como backend para banco de dados e autenticação segura.

    Pyppeteer para automação e web scraping robusto.

A segurança é um pilar central, com um sistema de login que valida a identidade do usuário através de HWID (Hardware ID), garantindo que o acesso seja restrito a dispositivos autorizados.
✨ Funcionalidades Principais

Recurso
	

Descrição

🔐 Autenticação Segura
	

Login com Supabase e verificação de HWID para máxima segurança.

🗂️ Gerenciamento CRUD
	

Crie, visualize, edite e exclua contas (mestras ou comuns) diretamente pela interface.

🤖 Automação Inteligente
	

Utiliza Pyppeteer para automatizar o envio de créditos R6 de forma eficiente.

💻 Interface Híbrida
	

O melhor dos dois mundos: um CLI rápido com Rich e uma GUI intuitiva com pywebview.

⚡ Operação Multithread
	

Executa tarefas de automação em threads separadas para não bloquear a interface do usuário.

🛒 Seleção Visual de Itens
	

Uma janela web (HTML/CSS/JS) permite escolher facilmente o item para compra.
🔄 Como Funciona (Fluxo de Uso)

O fluxo de operação foi projetado para ser intuitivo e direto, guiando o usuário em cada etapa do processo.

graph LR
    A[Início] --> B(🔐 Login Seguro com HWID);
    B --> C{MENU PRINCIPAL};
    C --> D(➕ Adicionar Conta);
    D --> E{Mestra ou Comum?};
    E --> C;
    C --> F(🛒 Enviar Créditos);
    F --> G[🖼️ Escolher Item<br>(Janela pywebview)];
    G --> H(💸 Definir Limite de Gastos);
    H --> I(🚀 Iniciar Envio Automatizado);
    I -- Atualiza BD --> J[📊 Créditos da Conta];
    I --> C;

Passo a Passo:

    Login: O usuário inicia a aplicação e realiza o login, que é validado pelo Supabase e pelo HWID do dispositivo.

    Gerenciamento de Contas: No menu, o usuário pode adicionar novas contas, definindo-as como "mestra" (de onde saem os créditos) ou "comum" (que recebe os créditos).

    Seleção de Itens: Ao optar por enviar créditos, uma janela pywebview é aberta, exibindo uma interface web (HTML/CSS/JS) onde o usuário pode visualizar e selecionar o item desejado para a "compra".

    Configuração: O usuário define a quantidade máxima de créditos que a conta mestra pode gastar na operação.

    Automação: A aplicação inicia o processo de automação com Pyppeteer em uma thread separada, realizando a transferência dos créditos.

    Atualização: Ao final, a quantidade de créditos em cada conta envolvida é atualizada automaticamente no banco de dados.

    Retorno: A aplicação informa o sucesso da operação e retorna ao menu principal.

🛠️ Tecnologias e Arquitetura

O sistema integra uma CLI e uma GUI para uma experiência de usuário completa e eficiente.

graph TD
    subgraph "Interface do Usuário"
        A[👤 Usuário] --> B{💻 CLI (Rich)};
        B -- Abre Janela --> C[🖼️ GUI Web (pywebview)];
        C -- Retorna Seleção --> B;
    end

    subgraph "Backend & Segurança"
        B --> D{🔐 Autenticação};
        D --> E[🛡️ Validação de HWID];
        D --> F[☁️ Supabase Auth];
    end

    subgraph "Core de Automação (Multithread)"
        B --> G[⚙️ Gerenciador de Tarefas];
        G -- Inicia Thread --> H[🤖 Scraper (Pyppeteer)];
        H -- Gerencia Sessão --> I[📄 sessions.json];
        H -- Interage com --> J[🌐 Website Externo];
    end

    subgraph "Banco de Dados"
        B --> K[🗄️ CRUD de Contas];
        K <--> L[☁️ Supabase DB];
    end

📦 Estrutura do Projeto

UbiOver-CLI/
├── main.py                # Ponto de entrada da aplicação
├── core/
│   ├── auth.py            # Lógica de autenticação (Supabase, HWID)
│   ├── scraper.py         # Lógica de automação (Pyppeteer)
│   └── manager.py         # Funções CRUD para gerenciamento de contas
├── ui/
│   ├── components.py      # Componentes de UI reutilizáveis (tabelas, painéis)
│   └── screens.py         # Telas da aplicação (login, menu principal)
├── webview/
│   ├── index.html         # Estrutura da GUI de seleção de itens
│   ├── style.css          # Estilos da GUI
│   └── script.js          # Lógica de interação da GUI
├── database.py            # Módulo de conexão com o Supabase
├── sessions/              # Diretório para armazenar sessões de login .json
└── README.md              # Esta documentação

🤝 Como Contribuir

Contribuições são o que tornam a comunidade open-source um lugar incrível para aprender, inspirar e criar. Qualquer contribuição que você fizer será muito apreciada.

    Faça um Fork do projeto.

    Crie sua Feature Branch (git checkout -b feature/AmazingFeature).

    Faça o Commit de suas mudanças (git commit -m 'Add some AmazingFeature').

    Faça o Push para a Branch (git push origin feature/AmazingFeature).

    Abra um Pull Request.

📄 Licença

Distribuído sob a Licença MIT. Veja o arquivo LICENSE para mais informações.
👨‍💻 Desenvolvedor

<div align="center">

Vinícius Ansbach Costa

</div>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColor=7B2CBF,97266D,40B5A4&height=120&section=footer&animation=fadeIn" />
</div>
