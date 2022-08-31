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

# Contribuições

Sinta-se a vontade para realizar adicionar mais informações ou realizar correções. Fork me!

# Referências

- [git - guides](https://github.com/git-guides/git-commit)
- [git - book](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Obtendo-um-Reposit%C3%B3rio-Git)
- [git - guia prático](http://rogerdudler.github.io/git-guide/index.pt_BR.html)
- [git - comandos - leocomelli](https://gist.github.com/leocomelli/2545add34e4fec21ec16)
