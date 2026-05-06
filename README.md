# 📘 Guia de Aprendizado — Git & GitHub
 
Repositório de estudos com anotações, comandos e conceitos aprendidos ao longo do curso de Git & GitHub.
Cada arquivo representa um tópico estudado com explicações práticas e exemplos reais.
 
---
 
## 🗂️ Estrutura do Repositório
 
```
📁 projeto/
├── README.md                        ← você está aqui
├── ola_mundo.py                     ← primeiro arquivo de teste
├── .gitignore                       ← arquivos ignorados pelo Git
├── comandos_bash.txt                ← comandos essenciais do terminal
├── Resumo_Bash_e_Git                ← resumo geral de Git + Bash
├── Comando_git.txt                  ← comandos principais do Git
├── Comando_git_secundarios.txt      ← comandos avançados do Git
├── gitignore-e-gitkeep.txt          ← o que são e como usar
├── GitHub_e_Fluxo_de_Trabalho.txt  ← fluxo local → remoto
├── VScode_PadronizacaoFlow.txt      ← VS Code, Git Flow e boas práticas
├── Branches.txt                     ← o que são branches e como usar
└── Fork.txt                         ← fork, clone e pull request
```
 
---
 
## 📚 Conteúdo Estudado
 
### 1. Bash — Terminal
> Arquivo: `comandos_bash.txt`
 
Comandos básicos para navegar e manipular arquivos pelo terminal antes de começar com o Git.
 
| Comando | O que faz |
|---|---|
| `ls` | Lista arquivos da pasta |
| `ls -a` | Lista tudo, incluindo ocultos |
| `cd <pasta>` | Entra em um diretório |
| `cd ..` | Volta uma pasta |
| `pwd` | Mostra o caminho atual |
| `mkdir <nome>` | Cria uma pasta |
| `rm <arquivo>` | Remove um arquivo |
| `rm -rf <pasta>` | Remove pasta inteira ⚠️ |
| `cat <arquivo>` | Mostra conteúdo do arquivo |
| `nano <arquivo>` | Cria ou edita arquivo pelo terminal |
 
---
 
### 2. Git — Controle de Versão
> Arquivos: `Resumo_Bash_e_Git`, `Comando_git.txt`, `Comando_git_secundarios.txt`
 
O Git é um sistema de versionamento que permite salvar e controlar versões do projeto.
Cada commit é como uma "foto" do estado do projeto naquele momento.
 
**Fluxo local básico:**
```
Editar arquivos → git add → git commit → repetir
```
 
**Comandos principais:**
 
```bash
git init          # inicia o repositório na pasta atual
git status        # mostra o estado dos arquivos
git add <arquivo> # prepara o arquivo para o commit
git commit -m ""  # salva um checkpoint com descrição
git log           # visualiza o histórico de commits
git diff <arquivo># mostra as diferenças entre versões
git reset <arquivo># tira o arquivo do stage (desfaz o git add)
git fetch         # traz branches do GitHub para o local
```
 
---
 
### 3. .gitignore e .gitkeep
> Arquivo: `gitignore-e-gitkeep.txt`
 
**`.gitignore`** — diz ao Git quais arquivos **não** rastrear.
 
```
*.pptx
*.xlsx
*.csv
*.xls
*.parquet
```
 
O `*` é um curinga: `*.csv` ignora qualquer arquivo com extensão `.csv`.
 
**`.gitkeep`** — arquivo vazio que força o Git a rastrear pastas vazias,
já que o Git não rastreia pastas sem conteúdo por padrão.
 
```bash
touch nome-da-pasta/.gitkeep
```
 
---
 
### 4. GitHub e Fluxo de Trabalho
> Arquivo: `GitHub_e_Fluxo_de_Trabalho.txt`
 
O GitHub é a plataforma online onde o repositório fica na nuvem.
Após o commit, o trabalho ainda está apenas na máquina local — é preciso fazer o **push**.
 
**Conectar o projeto ao GitHub (uma única vez):**
```bash
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
git branch -M main
git push -u origin main
```
 
**Fluxo do dia a dia:**
```
Salvar (Ctrl+S) → Stage (+) → Commit → Sync Changes (Push)
```
 
> 💡 Sempre faça `git pull` antes do `git push` para evitar conflitos.
 
---
 
### 5. VS Code e Git Flow
> Arquivo: `VScode_PadronizacaoFlow.txt`
 
O VS Code centraliza tudo em um lugar: arquivos, terminal e controle de versão.
A aba gráfica de Source Control permite fazer add, commit e push sem digitar comandos.
 
**Git Flow — regra principal:**
- ❌ Nunca trabalhe diretamente na branch `main`
- ✅ Use a branch `develop` para o dia a dia
- ✅ Só faça merge para `main` quando o código estiver estável
**Padrão de commits (Conventional Commits):**
 
```
feat: adiciona nova funcionalidade
fix: corrige um bug
docs: atualiza documentação
refactor: melhora o código sem mudar comportamento
```
 
---
 
### 6. Branches
> Arquivo: `Branches.txt`
 
Branches são "universos paralelos" do código. Permitem desenvolver funcionalidades
ou corrigir erros sem afetar a versão estável do projeto.
 
```bash
git branch                        # lista as branches
git branch nome-da-branch         # cria uma nova branch
git checkout nome-da-branch       # muda para uma branch
git checkout -b nova-branch       # cria e muda ao mesmo tempo
git merge nome-da-branch          # une a branch atual com outra
git branch -d nome-da-branch      # deleta a branch
```
 
**Fluxo típico:**
```
main → cria branch → faz alterações → commit → volta pra main → merge → deleta branch
```
 
---
 
### 7. Fork e Pull Request
> Arquivo: `Fork.txt`
 
**Fork** — cópia de um repositório de outra pessoa para a sua conta no GitHub.
Permite estudar, modificar e experimentar sem afetar o original.
 
**Fluxo com fork:**
```
Fork (GitHub) → Clone (máquina local) → Editar → Commit → Push → Pull Request
```
 
**Pull Request** — pedido para o dono do repositório original aceitar suas alterações.
 
Para manter o fork atualizado:
```bash
git remote add upstream https://github.com/usuario-original/repositorio.git
git fetch upstream
git merge upstream/main
```
 
---
 
## 🔗 Referências
 
- [Playlist do Curso — Introdução ao Git e GitHub (YouTube)](https://www.youtube.com/watch?v=84FhNXNWoig&list=PLvlkVRRKOYFQyKmdrassLNxkzSMM6tcSL)
- [Conventional Commits](https://medium.com/@BradleyOThompson/conventional-commits-ffad83dfe561)
- [Padrões de nomenclatura para branches e commits](https://medium.com/prolog-app/nossos-padr%C3%B5es-de-nomenclatura-para-branches-e-commits-fade8fd17106)
- [Conventional Commits Pattern](https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657)
 
