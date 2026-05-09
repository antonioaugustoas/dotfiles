# 💻 GUTO-PLATFORM COCKPIT // Dotfiles

> *"Your development environment is your Formula 1 cockpit. It should be engineered for maximum speed, ergonomics, and absolute automation."*

Este repositório contém as configurações de estação de trabalho, atalhos de terminal, temas de IDE e scripts de provisionamento automatizados do ecossistema de desenvolvimento da **Baseloop Engineering**. O objetivo central é o **onboarding de máquina em 5 minutos**: sair de um sistema operacional recém-instalado para um ambiente de engenharia pronto para produção com apenas um comando.

---

## 🏎️ O Conceito: Engenharia de Performance de Elite

Assim como um cockpit de F1 possui botões projetados milimetricamente para acesso instantâneo sem perda de foco, nosso ambiente de terminal e editor é projetado sob três princípios de elite:
1.  **Ergonomia de Dedos (Keyboard-Driven):** Redução total do uso do mouse através de aliases inteligentes, navegações rápidas e atalhos globais de IDE.
2.  **Aesthetics of Focus:** Uso de tipografias modernas com suporte a ligaturas (ex: *JetBrains Mono*, *Cascadia Code*), esquemas de cores de alta fidelidade e contraste balanceado para mitigar a fadiga visual durante jornadas longas de codificação.
3.  **Ambiente como Código (Environment-As-Code):** Nenhuma preferência de sistema é configurada manualmente; tudo é versionável, auditável e reprodutível.

---

## 🛠️ O que está Versionado Aqui (O Cockpit)

```
[ dotfiles/ ]
   ├── 🎨 cheatsheets/ ──── Folhas de dicas de ferramentas e padrões de design
   ├── 🐚 shell/ ───────── Perfis de terminal, prompts estéticos e aliases rápidos
   ├── 📝 vscode/ ──────── settings.json, keybindings.json e lista de extensões
   └── ⚙️ git/ ─────────── .gitconfig global higienizado (aliases de produtividade)
```

### 1. ⚙️ Git de Alta Performance (`.gitconfig`)
Nossos atalhos do Git eliminam comandos longos e trazem clareza para o histórico de branches:
*   `git s`: Status condensado de arquivos modificados.
*   `git co`: Checkout expresso de branches.
*   `git br`: Lista de branches ordenadas por data de commit.
*   `git l`: Histórico formatado em árvore gráfica e colorida com autores e datas relativas.

### 2. 📝 Perfil de VS Code Estabilizado
Configurações corporativas de renderização, salvamento atômico, formatação em salvamento (Prettier/ESLint), guias visuais de identação de profundidade e controle de zoom responsivo.

---

## 📈 Plano de Crescimento Técnico (Como se Destacar no Mercado)

Para transformar este repositório em uma vitrine mundial de engenharia de produtividade, execute os seguintes passos de expansão:

### 🚀 Fase 1: Estética de Terminal Avançada (Aparência F1)
*   **O Prompt de Elite (Oh-My-Posh):** Instalar e configurar o *Oh-My-Posh* para exibir informações ricas sobre a branch git ativa, status de arquivos modificados, ambiente Python virtual ativo, versão do Node.js instalada e tempo de execução do último comando.
*   **Fontes de Alta Fidelidade (Nerd Fonts):** Adotar fontes com suporte a glifos (ícones no terminal), como `JetBrains Mono NF` ou `Cascadia Code NF`.

### 🚀 Fase 2: Atalhos Rápidos e Automação (PowerShell de Alta Performance)
Expandir o perfil do PowerShell local para incluir aliases inteligentes de altíssima produtividade:
```powershell
# Exemplos de automações de teclado no terminal:
function g { git status }
function ll { Get-ChildItem -Force }
function codew { code e:\repos\repos.code-workspace } # Abre todo o workspace com 5 teclas
function pyenv { .venv\Scripts\Activate.ps1 } # Ativa ambiente virtual Python instantâneo
```

### 🚀 Fase 3: Provisionamento Automatizado (Script de 1 Clique)
Desenvolver o script `setup.ps1` utilizando o gerenciador de pacotes nativo do Windows (**winget**) para instalar todos os programas essenciais de forma silenciosa e automática:
```powershell
# Exemplo de provisionamento silencioso de estação de trabalho:
winget install -e --id Microsoft.VisualStudioCode
winget install -e --id Git.Git
winget install -e --id Docker.DockerDesktop
winget install -e --id Microsoft.DotNet.SDK.9
```

---

## 🛡️ Protocolo de Segurança de Segredos (Separation of Secrets)

### "Expor minhas dotfiles públicas pode me prejudicar ou revelar propriedade intelectual valiosa?"
**Não!** Exibir suas configurações de terminal, atalhos de Git e configurações visuais de IDE é uma das práticas mais respeitadas na engenharia de elite global. Não há nenhum segredo comercial ou de propriedade intelectual do monolito GUTO ou da Baseloop revelado nestes arquivos estéticos.

Contudo, para garantir que você nunca sofra exposição financeira ou vazamentos acidentais de segurança, adotamos o **Protocolo de Separação de Segredos**:

1.  **Regra de Ouro:** Dados sensíveis (como credenciais de bancos, chaves de API da OpenAI, tokens SSH ou senhas locais) **nunca** entram no diretório `dotfiles`.
2.  **Variáveis Globais de Ambiente:** Credenciais e tokens de APIs devem ser configurados no arquivo `.env` local em cada projeto, o qual fica estritamente listado no `.gitignore`.
3.  **Configurações Locais com Git Include:** Para manter seu e-mail corporativo ou chaves SSH específicas separadas do Git público, use a diretiva `includeIf` no seu `.gitconfig` global para carregar um arquivo `.gitconfig.local` que fica fora da pasta do repositório versionado público.

### 🔒 Varredura Automática (GitLeaks)
Este repositório possui proteção ativa de varredura estática de commits (GitHub Actions GitLeaks) para garantir que qualquer commit acidental contendo chaves ou segredos seja interceptado e bloqueado de forma automática antes de se tornar visível na nuvem.
