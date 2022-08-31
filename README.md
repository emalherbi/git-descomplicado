# git-descomplicado

Guia prático do git, sem complicação ;)

## Instalação

[Instalação GIT](https://emalherbi.github.io/aulas/programacao-web/aula-7-git/#/13)

## Configurações

- As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional; 
- (Ex.: Windows: C:\Users\NOME_PC\.gitconfig);
- As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima;

#### Setar usuário e e-mail

```sh
git config --global user.name "SEU NOME COMPLETO"
git config --global user.email "seu@email.com"
```

#### Listar configurações

```sh
git config --list
```

## Repositório Local

#### Criar novo repositório

Isso cria um novo subdiretório chamado **.git** que contém todos os arquivos necessários de seu repositório (um esqueleto de repositório Git):

```sh
git init 
```

#### Verificar estado dos arquivos/diretórios:

```sh
git status
```

#### Adicionar arquivo/diretório (staged area):

Adiciona os arquivos novos ou alterados em seu diretório de trabalho à área de preparação do Git. 

###### Adicionar todos os arquivos/diretórios

```sh
git add .
```

###### Adicionar um arquivo em específico

```sh
git add meu_arquivo.txt
```

###### Adicionar um diretório em específico

```sh
git add meu_diretorio
```

#### Comitar arquivo/diretório

- Para realmente confirmar estas mudanças (isto é, fazer um commit), use:
- Agora o arquivo é enviado para o HEAD, mas ainda não para o repositório remoto.

```sh
git commit -m "meu comentário"
```

###### Comitar arquivo específico informando uma mensagem

```sh
git commit meu_arquivo.txt -m "meu comentário"
```

#### Enviar arquivos/diretórios para o repositório remoto

O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

```sh
git push -u origin main
```

Os demais pushes não precisam dessa informação

```sh
git push
```

# Referências

- [git - guides](https://github.com/git-guides/git-commit)
- [git - book](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Obtendo-um-Reposit%C3%B3rio-Git)
- [git - guia prático](http://rogerdudler.github.io/git-guide/index.pt_BR.html)
- [git - comandos - leocomelli](https://gist.github.com/leocomelli/2545add34e4fec21ec16)



