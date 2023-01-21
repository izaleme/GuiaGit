# Guia de comandos básicos do git/github

###### Izabela Leme, 21/01/2023


Ao trabalhar com git, você frequentemente usará uma série de comandos padrões. Para facilitar o entendimento de novos programadores e auxiliar antigos que desejam relembrar, fiz esse guia rápido com um compilado dos principais comandos usados em git.

Antes de começar, você deve baixar e instalar o git através do link https://git-scm.com/download/win


### Comandos Gerais:

`git init` cria um novo repositório git

`git clone <https://link-com-o-nome-do-repositório>` cria uma cópia idêntica da versão mais recente de um projeto em um repositório, e o salva em seu computador

`git branch <nome-da-branch>` cria uma nova branch

`git push -u <local-remoto> <nome-da-branch>` envia sua branch para o repositório remoto

`git branch` ou `git branch --list` lista todas as branches

`git branch -d <nome-da-branch>` exclui uma branch

`git checkout <nome-da-branch>` troca da sua branch atual para a outra setada

`git checkout -b <nome-da-branch>` automaticamente cria nova branch e troca para ela

`git status` fornece informações sobre a branch atual

`git add <arquivo>` adiciona as alterações do arquivo citado no próximo commit

`git add -A` adiciona todas as alterações no próximo commit

`git commit -m "mensagem do commit"` salva suas alterações no espaço de trabalho local

`git push <repositório-remoto> <nome-da-branch>` faz o upload dos seus commits no repositório remoto (quando a branch já está no remoto)

`git push -u origin <nome-da-branch>` faz upload da branch nova e dos commits de uma vez (para branches novas)

`git pull <repositório-remoto>` recebe (git fetch) e aplica (git merge) as alterações do repositório remoto no espaço de trabalho local

`git log -- oneline` mostra o histórico de commits


### Desfazendo um commit com git revert
Para desfazer um commit, precisamos pegar o código hash ao lado do commit que desejamos desfazer. Para isso, primeiro usamos o `git log --online`. Em seguida, especificamos o código hash no seguinte comando: `git revert 3321844`, onde "3321844" é o número de exemplo. Isso abrirá uma tela, e você só precisa pressionar shift + q para fechá-la.
Interessante ressaltar que o git revert não altera o histórico de commits, pois ele cria um novo commit, sem excluir o antigo. Para as alterações funcionarem, você precisará dar um push no repositório remoto.


### Git Merge
Depois de concluir seu trabalho na sua branch, só resta fazer o git merge, que é o comando que unirá sua branch com o branch pai (geralmente, dev ou master/main).
Para isso, você deve estar dentro da branch pai, como a "dev", por exemplo:
```
git checkout dev
git pull
git merge <nome-da-branch-com-o-recurso>
```
