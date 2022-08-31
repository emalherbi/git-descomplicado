# git-descomplicado

Guia prático do git, sem complicação ;)

## Instalação

[Instalação GIT](https://emalherbi.github.io/aulas/programacao-web/aula-7-git/#/13)

## Configurações

- As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional; 
- (Ex.: Windows: C:\\Users\\NOME_PC\\.gitconfig);
- As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima;

#### Setar usuário e e-mail

```
git config --global user.name "SEU NOME COMPLETO"
git config --global user.email "seu@email.com"
```

#### Listar configurações

```
git config --list
```

# Repositório Local

## Baixar o projeto no computador usando a opção SSH e enviar para o GIT.

```
git init 
git add .
git commit -m "meu comentário"
git branch -M main
git remote add origin git@github.com:emalherbi/git-descomplicado.git
git push -u origin main
```

## Clonar um repositório remoto já existente

```
git clone git@github.com:emalherbi/git-descomplicado.git
```

## Criar novo repositório

Isso cria um novo subdiretório chamado **.git** que contém todos os arquivos necessários de seu repositório (um esqueleto de repositório Git):

```
git init 
```

## Verificar estado dos arquivos/diretórios:

```
git status
```

## Adicionar arquivo/diretório (staged area):

Adiciona os arquivos novos ou alterados em seu diretório de trabalho à área de preparação do Git. 

#### Adicionar todos os arquivos/diretórios

```
git add .
```

#### Adicionar um arquivo em específico

```
git add meu_arquivo.txt
```

#### Adicionar um diretório em específico

```
git add meu_diretorio
```

## Comitar arquivo/diretório

- Para realmente confirmar estas mudanças (isto é, fazer um commit), use:
- Agora o arquivo é enviado para o HEAD, mas ainda não para o repositório remoto.

```
git commit -m "meu comentário"
```

#### Comitar arquivo específico informando uma mensagem

```
git commit meu_arquivo.txt -m "meu comentário"
```

## Enviar arquivos/diretórios para o repositório remoto

O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

```
git push -u origin main
```

Os demais pushes não precisam dessa informação

```
git push
```

## Atualizar repositório local de acordo com o repositório remoto

#### Atualizar os arquivos no branch atual

```
git pull
```

#### Buscar as alterações, mas não aplica-las no branch atual

- `-p` = dizer ao git para remover do ramo local ramos remotos que não existem mais.

```
git fetch -p
```

## Branches

- O **main** ou **master** é o branch principal do GIT.
- O **HEAD** é um ponteiro _especial_ que indica qual é o branch atual. Por padrão, o **HEAD** aponta para o branch principal, o **main** ou **master**.

#### Criando um novo branch

```
git branch bug-123
```

#### Trocando para um branch existente

```
git checkout bug-123
```

Neste caso, o ponteiro principal **HEAD** esta apontando para o branch chamado **bug-123**.

#### Criar um novo branch e trocar

```
git checkout -b bug-456
```

#### Voltar para o branch principal (master)

```
git checkout master
```

#### Apagando um branch

```
git branch -D bug-123
```

## Listar branches

#### Listar branches

```
git branch
```

###### Listar branches com informações dos últimos commits

```
git branch -v
```

###### Listar branches que já foram fundidos (merged) com o **master**

```
git branch --merged
```

###### Listar branches que não foram fundidos (merged) com o **master**

```
git branch --no-merged
```

## Criando branches no repositório remoto

#### Criando um branch remoto com o mesmo nome

```
git push origin bug-123
```

##### Baixar um branch remoto para edição

```
git checkout -b bug-123 origin/bug-123
```

##### Apagar branch remoto

```
git push origin:bug-123
```

## Visualizar histórico

#### Exibir histórico
	
```
git log
```

#### Exibir histórico com diff das duas últimas alterações

```
git log -p -2
```
	
#### Exibir informações resumidas em uma linha (hash completa e comentário)

```
git log --pretty=oneline
```
	
#### Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)

```
git log --pretty=format:"%h - %an, %ar : %s"
```
 
* %h: Abreviação do hash;
* %an: Nome do autor;
* %ar: Data;
* %s: Comentário.

#### Exibir histório de um determinado autor

```
git log --author=usuario
```

Verifique as demais opções de formatação no [Git Book](http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History)

## Rebasing

Quando é necessário atualizar a branch **xyz** com as atualizações da **main**

```
git rebase main
```

Fazendo o **rebase**. Atualizar a branch **xyz** com a **main**

```
git checkout xyz
git fetch origin main
git rebase origin/main
# Corrigir os conflitos
git rebase --continue # ou git rebase --skip
git push --force-with-lease
```

Mais informações e explicações sobre o [Rebasing](http://git-scm.com/book/en/Git-Branching-Rebasing)

## Stash

- Para alternar entre um branch e outro é necessário fazer o commit das alterações atuais para depois trocar para um outro branch. Se existir a necessidade de realizar a troca sem fazer o commit é possível criar um **stash**. 
- O Stash como se fosse um branch temporário que contem apenas as alterações ainda não commitadas.

#### Criar um stash

```
git stash
```

#### Listar stashes

```
git stash list
```

#### Voltar para o último stash

```
git stash apply
```

#### Criar um branch a partir de um stash

```
git stash branch meu_branch
```

# Repositório Remoto

#### Exibir os repositórios remotos

```
git remote -v
```

#### Exibir informações dos repositórios remotos

```
git remote show origin
```
	
# Git Alias

- As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional; 
- (Ex.: Windows: C:\\Users\\NOME_PC\\.gitconfig);
 
```
[user]
  email = seu@email.com
  name = SEU NOME COMPLETO
[alias]
  ad = add *
  br = branch
  brd = branch -D
  ch = checkout
  chb = checkout -b
  cl = clone
  co = commit -m
  df = diff
  ft = fetch -p
  pl = pull
  ps = push
  psf = push --force-with-lease
  rb = rebase origin/main
  rbc = rebase --continue
  rbs = rebase --skip
  rs = reset --hard HEAD
  st = status -sb
  up = pull
```

#### Listar configurações

```
git config --list
```

# Contribuições

Sinta-se a vontade para realizar adicionar mais informações ou realizar correções. Fork me!

# Referências

- [git - guides](https://github.com/git-guides/git-commit)
- [git - book](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Obtendo-um-Reposit%C3%B3rio-Git)
- [git - guia prático](http://rogerdudler.github.io/git-guide/index.pt_BR.html)
- [git - comandos - leocomelli](https://gist.github.com/leocomelli/2545add34e4fec21ec16)
