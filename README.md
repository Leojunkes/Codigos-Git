# Códigos-Git

códigos úteis no GIT

## Índice

- [Ajuda comandos específicos](#Ajuda-comandos-específicos)
- [Setar Usuário](#Setar-Usuário)
- [Setar Usuário](#Setar-Usuário)
- [Setar Email:](#Setar-Email)
- [Setar Editor:](#Setar-Editor)
- [Setar ferramenta de merde](#Setar-ferramenta-de-merde)
- [Setar arquivos a serem ignorados](#Setar-arquivos-a-serem-ignorados)
- [Listar configurações](#Listar-configurações)
- [Criar novo repositório Local](#Criar-novo-repositório-Local)
- [Verificar estado dos arquivos/diretórios](#Verificar-estado-dos-arquivos/diretórios)
- [Adicionar um arquivo em específico](#Adicionar-um-arquivo-em-específico) 
- [Exibir histórico com diff, duas alterações](#Exibir-histórico-com-diff-das-duas-últimas-alterações)
- [Exibir histório de um arquivo específico](#Exibir-histório-de-um-arquivo-específico)

## Ajuda comandos específicos:

`git help add`
`git help commit`
`git help <qualquer comando git>`

## Setar Usuário:

`git config --global user.name "seu nome"`

## Setar Email:

`git config --global user.email "seu email"`

## Setar editor:

`git config --global core.editor seu editor`

## Setar ferramenta de merge:

`git config --global merge.tool vimdiff`

## Setar arquivos a serem ignorados:

`git config --global core.excludesfile ~/.gitignore`

## Listar configurações:

`git config --listgit`

## Criar novo repositório Local:

`git init`

## Verificar estado dos arquivos/diretórios:

`git status`

## Adicionar um arquivo em específico:

`git add meu_arquivo.txt` [Inicio](#Códigos-Git)

## Exibir histórico com diff das duas últimas alterações:

`git log -p -2`

## Exibir histório de um arquivo específico:

`git log -- <caminho_do_arquivo>`

## Desfazendo alteração local (working directory) OBS: quando o arquivo não foi adicionado na estaged area:

`git checkout -- meu_arquivo.txt`

## Desfazendo alteração local (staging area):

`git reset HEAD meu_arquivo.txt`

## A alteração do diretório pode ser realizada através do comando abaixo:

`git checkout meu_arquivo.txt`

## Repositório Remoto:

`git remote`

## Exibir os repositórios remotos:

`git remote -v`

## Vincular repositório local com um repositório remoto

`git remote add origin git@github.com:Leojunkes/seuRepositório`

## Exibir informações dos repositórios remotos

`git remote show origin`

Renomear um repositório remoto

`git remote rename origin curso-git`

Desvincular um repositório remoto

`git remote rm curso-git`

O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

`git push -u origin main`

Os demais pushes não precisam dessa informação

`git push`

Atualizar os arquivos no branch atual

`git pull`

Clonar um repositório remoto já existente

`git clone git@github.com:leocomelli/seuRepositório.git`

Tags

Criando uma tag leve

`git tag vs-1.1`

Criando uma tag anotada

`git tag -a vs-1.1 -m "Minha versão 1.1"`

Criando uma tag assinada

Para criar uma tag assinada é necessário uma chave privada (GNU Privacy Guard - GPG).

`git tag -s vs-1.1 -m "Minha tag assinada 1.1"`

Criando tag a partir de um commit (hash)

`git tag -a vs-1.2 9fceb02`

Criando tags no repositório remoto

`git push origin vs-1.2`

Criando todas as tags locais no repositório remoto

`git push origin --tags`

O Master é o Branch principal do GIT.

Criando um novo branch

`git branch bug-123`

Trocando para um branch existente

`git checkout bug-123`

Neste caso, o ponteiro principal HEAD esta apontando para o branch chamado bug-123.

Criar um novo branch e trocar

`git checkout -b bug-456`

Voltar para o branch principal (master)

`git checkout master`

Resolver merge entre os branches

`git merge bug-123`

Para realizar o merge, é necessário estar no branch que deverá receber as alterações. O merge pode automático ou manual. O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.

A mensagem indicando um merge manual será:

Automerging meu_arquivo.txt

CONFLICT (content): Merge conflict in meu_arquivo.txt
Automatic merge failed; fix conflicts and then commit the result.
Apagando um branch

`git branch -d bug-123`

Listar branches

`git branch`

Listar branches com informações dos últimos commits

`git branch -v`

Listar branches que já foram fundidos (merged) com o master

`git branch --merged`

Listar branches que não foram fundidos (merged) com o master

`git branch --no-merged`

Criando um branch remoto com o mesmo nome

`git push origin bug-123:new-branch`

Baixar um branch remoto para edição

`git checkout -b bug-123 origin/bug-123`

Apagar branch remoto

`git push origin:bug-123`

Rebasing

Fazendo o rebase entre um o branch bug-123 e o master.

`git checkout experiment`

`git rebase master`

###Stash

Para alternar entre um branch e outro é necessário fazer o commit das alterações atuais para depois trocar para um outro branch. Se existir a necessidade de realizar a troca sem fazer o commit é possível criar um stash. O Stash como se fosse um branch temporário que contem apenas as alterações ainda não commitadas.

Criar um stash

`git stash`

Listar stashes

`git stash list`

Voltar para o último stash

`git stash apply`

Voltar para um stash específico

`git stash apply stash@{2}`

Onde 2 é o indíce do stash desejado.
