### PRINCIPAIS COMANDOS DE UM FLOW


##Começar uma nova funcionalidade
O desenvolvimento de novas funcionalidades começa no branch 'develop'.

##Comece o desenvolvimento de uma nova funcionalidade com

git flow feature start MYFEATURE
Esse comando cria um novo branch da funcionalidade baseado no 'develop' e alterna para ele

###Finalizar uma funcionalidade

##Finaliza o desenvolvimento de uma funcionalidade. Esse comando faz o seguinte

Mescla MYFEATURE no 'develop'
Remove o branch da funcionalidade
Volta para o branch 'develop'
git flow feature finish MYFEATURE
Publicar uma funcionalidade
Você está desenvolvendo uma funcionalidade colaborativamente?
Publique uma funcionalidade para o servidor remoto, assim ela pode ser utilizada por outros usuários.

git flow feature publish MYFEATURE
Obter uma funcionalidade publicada
Obtenha uma funcionalidade publicada por outro usuário e acompanhe as alterações remotas.

git flow feature pull MYFEATURE
Criar uma versão/release
Auxilia a preparação de uma nova versão de produção
Permite correções de bugs menores e a preparação de metadados de uma versão
★ ★ ★

##Começar uma versão
Para começar uma versão, use o comando git flow release. Ele
cria um branch da versão baseado no branch 'develop'.

git flow release start RELEASE [BASE]
Você pode opcionalmente fornecer um hash sha-1 do commit [BASE] de onde começar a versão. O commit precisa estar no branch 'develop'

★ ★ ★

##É sensato publicar o branch da versão depois de criá-lo, para permitir commits por outros desenvolvedores. É semelhante à publicação de uma funcionalidade com o comando:

git flow release publish RELEASE
(Você pode acompanhar uma versão remota com o comando
git flow release track RELEASE)

## Finalizar uma versão
A finalização de uma versão é um dos grandes passos na ramificação/branching do git. Ele executa várias ações:

Mescla o branch da versão no 'master'
Etiqueta a versão com seu nome
Mescla o branch da versão de volta no 'develop'
Remove o branch da versão
git flow release finish RELEASE
Hotfixes
Os hotfixes surgem da necessidade de agir imediatamente sobre uma situação indesejada na versão de produção ativa
Pode ser criado a partir da tag correspondente no branch master que indica a versão em produção.
★ ★ ★

git flow hotfix start
Assim como os outros comandos do git flow, um hotfix inicia com

git flow hotfix start RELEASE
O argumento release nesse caso marca a versão defeituosa na produção

## Finalizar um hotfix
Ao finalizar um hotfix ele é mesclado tanto no develop quanto no master. Além disso, o merge no master é etiquetado.

git flow hotfix finish RELEASE