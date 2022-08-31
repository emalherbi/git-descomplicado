# git-descomplicado

Guia prático do git, sem complicação ;)

## Instalação

[Instalação e Configuração do GIT](https://emalherbi.github.io/aulas/programacao-web/aula-7-git/#/13)

## Baixar o Projeto no PC

Baixar o projeto no computador usando a opção SSH.

```sh
mkdir meu_diretorio_pc
cd meu_diretorio_pc
git init 
git add .
git commit -m "meu comentário"
git branch -M main
git remote add origin git@github.com:SEU_USUARIO/SEU_REPOSITORIO.git
git push -u origin main
```

### Entendendo os comandos

Isso cria um novo subdiretório chamado **.git** que contém todos os arquivos necessários de seu repositório (um esqueleto de repositório Git).

```sh
git init 
```

Adiciona os arquivos novos ou alterados em seu diretório de trabalho à área de preparação do Git. 

```sh
git add .
```

Para realmente confirmar estas mudanças (isto é, fazer um commit), use:

```sh
git commit -m "meu comentário"
```

Agora o arquivo é enviado para o HEAD, mas ainda não para o repositório remoto.

```sh
git push -u origin main
```

# Referências

- [git - guides](https://github.com/git-guides/git-commit)
- [git - book](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Obtendo-um-Reposit%C3%B3rio-Git)
- [git - guia prático](http://rogerdudler.github.io/git-guide/index.pt_BR.html)



