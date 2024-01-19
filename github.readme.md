
# COMANDOS DO GIT PARA SALVAR A PRIMEIRA VERSÃO:
## comandos do git: obs. os comandos abaixo sao usados dentro do GIT BASH.

ls
vai listar os arquivos da pasta que você esta.

git init
vai iniciar o repositorio do git na pasta que você esta.

git add . 
vai colocar os arquivos em um local temporário. vc coloca os arquivos que quiser nessa area temporaria. 
se nao quiser colocar todos os arquivos não precisa colocar, mas em geral se coloca sim todos os arquivos.

obs git status
ele vai mostrar pra mim o status do projeto. posso usar esse comando se eu quiser, depois por exemplo de fazer o git add. acima

git commit -m "mensagem que voce quiser"
vou colocar entre aspas uma mensagem explicativa com o que eu fiz ate o momento.
mas nesse momento ele ainda não enviou isso para o github, isso vai ser feito com o comando push mais abaixo

obs git status
posso agora novamente dar um git status, que vai mostrar o commit que eu acabei de fazer

git branch -M main
github usa o nome main para salvar o historico de commits. antigamente usava o comando master. 
ideal é que seja o comando main. então para garantir que seja usado o comando main, fazemos esse codigo git branch -M main

obs agora o ideal é ir no site do GITHUB e criar um novo projeto vazio por lá. 
### **obs escolher o SSH (por isso que o link começará com git@github.com:wwddnn ... )
o próximo passo então é voltar para o GIT BASH e então vamos usar o comando abaixo, para ele associar esse projeto do meu computador com o repositório que acabei de criar la no github site.

### obs dica: para limpar o terminal do GIT BASH usar o comando clear

git remote add origin git@github.comseuusuario/seuprojeto.git
esse comando inteiro acima, que é um comando grande, você pode pegar direto na página do GITHUB site do repositório que acabei de criar
agora sim, nesse momento o meu repositório local esta associado com o meu repositório no site do GITHUB

git push -u origin main
pronto, agora é só enviar para o repositório do GITHUB!!!!


# COMANDOS DO GIT PARA SALVAR UMA NOVA VERSÃO: 
## é você fazer uma modificação no projeto e então salvar uma nova versão.
## vamos dizer que eu alterei algo simples no meu projeto, nesse exemplo alterei algo no arquivo vendas.html

git status
para mostrar como esta o nosso projeto

git add .
para ele adicionar na área temporária essa mudança

git commit -m "Acrescentado valor das vendas"
vai registrar o nosso commit, que foi a nossa alteração

git push
agora como já não é mais a primeira vez, é só fazer o simples comando git push, que ele já envia tudo

******************************************************************************************

# COMANDOS PARA VER E REGISTRAR SUA IDENTIFICAÇÃO: 
## para ver o name e email:

git config -- global user.name "seu name"
vai configurar meu nome

git config --global user.mail "seu email"
vai configurar seu email

git config --list
aparece as configurações todas 

**********************************************************************************
# COMO ENXERGAR ARQUIVOS OCULTOS:

ir em menu inciar no windows, depois em desmarcar a opção 'ocultar as extensões dos tipos de arquivos conhecidos'.
e depois marcar a opção 'mostrar arquivos, pastas e unidades ocultas'

**********************************************************************************
# CONFIGURAR CHAVE SSH PARA O GITHUB:
## vai cadastrar qual computador pode ser usado no seu nome.

passo a passo:
tem que gerar uma chave SSH no github.
obs buscar no google como gerar chave ssh no github.

usar o seguinte comando no gitbash:
ssh-keygen -t rsa -b 4096 -c "seu email"

pronto, agora ja foi gerada a chave ssh no computador, então eu pego essa chave que gerou que fica dentro do arquivo no seu computador...
e então copio a chave e colo la no site github em settings.

**********************************************************************************
# CLONAR O PROJETO E O HISTORICO QUE ESTA NO GITHUB PARA O MEU COMPUTADOR:

passo1: 
git clone git@github.com...
vou copiar atraves do clone o projeto que esta la no github, para o meu computador.
obs. vai clicar no botao que tem o endereco do projeto, pq ele vai trazer para o clone o historico de versoes.
obs copiar o link no formato SSH
atencao nao vai clicar em fazer download nao, pq aqui ele nao traz o historico de versoes.
### obs se precisar trocar de pasta dentro do git bash, basta usar o comando 'cd' e depois o nome da pasta que voce quer ir.
### obs se quiser abrir o vscode dentro do git bash é só usar o comando 'code . '

passo2:
git add .
vou adicionar os arquivos na minha area stage.

passo3:
git commit -m "mensagem explicativa"
esse comando é pra salvar as alterações no meu computador.

passo4:
git push
é pra mandar para o repositório remoto.
obs se for a primeira vez que vc atua nesse projeto, entao tem que fazer o comando 'git push -u origin main' ao inves desse comando acima que é somente o git push.

obs git log
esse comando mostra o historico de versoes do projeto.
da pra fazer varios git add . e ele vai juntando todas essas adições na area de stage, mas ainda nao fez commmit nem nada.
obs quando chamar  o git lob, e aparecer do lado do commit o texto 'origin/main, origin/HEAD' significa que ate aqui esta salvo la no github, 
mas dai pra cima é pq ainda nao esta salvo la no github.

***********************************************************************************************************************************
# GIT LOG PARA VERIFICAR O HISTORICO DE VERSÕES:

git log
mostra o histórico de versões

git log --oneline
ele mostra de forma resumida o histórico de versões do projeto.

***************************************************************************
# ENTENDENDO  GIT STATUS, GIT ADD E STAGE:

git status
informa o status do projeto naquele momento.
obs nesse comando, pode aparecer 3 situações: 
* modified
* untracked : é quando tem arquivo novo que eu criei mas ainda não salvei na area de stage. exemplo quando crio uma pagina html nova no meu projeto. aparece no gitbash como 'untracked files'.
* deleted : é quando você deleta algum arquivo, ele diz então que isso ocorreu.

git reset
obs se quiser usar esse comando, ele tira do stage as alterações que fiz agora há pouco como comando git add .

### GIT ADD . SOBRE.HTML
### se quiser adicionar somente alguns arquivos, e não todos. nesse caso somente o arquivo 'sobre.html' que eu quis adicionar. depois na sequência só fazer um git commit -m "mensagem".

git status
obs onde aparece no gitbash assim... 'HEAD > main' é porque eu fiz o add . e fiz o commit, porem ainda não fiz o push então ele ainda não foi para o repositório remoto do github.

***************************************************************************************
## GIT DIFF: DIFF QUER DIZER DIFERENÇA

dica usar o vscode que ele mostra as diferenças

git diff vendas.html
esse 'vendas.html' é o nome do arquivo que você quer ver a diferença, o que aconteceu com esse arquivo.

obs da pra consultar esse diff pelo vscode, fica ate melhor pra ver, basta ir no simbolo de compartilhar que fica do lado esquerdo da tela e depois em 'changes'.
entao da pra ver o que eu fiz desde o último commit até o momento de agora. fica em verde o que fiz de novo.

**************************************************************************************************
## GIT CHECKOUT

vamos usar bastante! os meus arquivos são modificados temporariamente para voltar do jeito que estava antes, mas tem que colocar o código para onde você quer modificar.

git checkout f225...
faz o comando e coloca o código que deseja que ele volte para aquele commit anterior.
isso é bom se você apagou arquivos ou tinha modificado errado depois. daí ele pode voltar para a posição que desejar.
OBS atenção!!! QUANDO DER O GIT CHECKOUT NÃO É PARA MEXER AGORA NOS ARQUIVOS, NÃO ALTERAR ELES AQUI. não alterar o commit que esta abaixo do head. não é uma boa prática isso. esse git checkout é só para ver mesmo o código no commit anterior. mas caso fez alguma mudança, então usar os comandos abaixo para desfazer as mudanças:
git reset
git clean -df
git checkout -- .
esse é um checkout para limpar modificações que fez de forma equivocada.

git checkout main
obs quando a gente volta, mas depois quer retornar para o mais recente commit feito.

git checkout HEAD~1
estou voltando para o penúltimo commit.
esse '~1' que na verdade é um '~N' ele indica que pode voltar n commits.


### CODIGO DO COMMIT, HEAD

cada commit la no github tem um código. se dermos o comando no gitbash, o comando git log, da pra ver esse codigo de cada commit.
o ultimo commit feito, ele vem com o 'HEAD -> main' significa que é o último commit feito ou seja esta nas cabeças.

***********************************************************************************************************************
## ARQUIVO .GITIGNORE

é um arquivo que indica o que não deve ser salvo pelo git. exemplo arquivos de log, arquivos compilados, arquivos de bibliotecas externas usadas no projeto, arquivos de configuração da IDE, arquivos de configuração do sistema.

no caso então o que eu não quero salvar no git, eu tenho que colocar o .gitignore

esse arquivo fica salvo na pasta principal do repositório. 

mas dá para salvar outros arquivos .gitignore em outras subpastas.

*****************************************************************************************************************
## REMOVENDO ARQUIVOS DA AREA DE STAGE

git status
é sempre bom dar esse comando antes pra ver como esta 

git reset

****************************************************************************************************************
## COMO DESFAZER MODIFICACOES NAO SALVAS
# VC APAGA AS MODIFICACOES DESDE O ULTIMO COMMIT

git status

git reset
nesse caso para tirar do stage as ultimas alteracoes

git clean -df

git checkout -- .
agora sim depois desses comandos ele voltou para o que estava antes, posso ir la no programa que vai estar do jeito que estava antes, ele reparou.
****************************************************************************************************************
## O QUE FAZER QUANDO ABRE O EDITOR VIM
# é o editor básico do linux, ele funciona sem ter uma interface gráfica. 
# ele também esta presente no gitbash.


i
habilita para escrever dentro do vim
posso escrever o que quiser agora, pois é a msg que vem no -m "..." do commit que eu não completei antes, por isso abre esse editor vim do linux.

ESC
wq
ENTER
primeiro aperta o esc, e depois digita o wq. isso é pra salvar o commit

ESC
q!
ENTER
aqui ele não salva as alterações do commit que deixei incompleto, ele sai da tela mesmo do vim.

*****************************************************************************************************************
## DELETANDO O ÚLTIMO COMMIT SEM DELETAR MODIFICAÇÕES NO ARQUIVO
# DESFAZER O ÚLTIMO COMMIT
# nesse caso eu quero desfazer o último commit que acabei de fazer, porque eu esqueci de fazer alguma coisinha nos arquivos. então vou desfazer esse commit, mas sem mexer nas modificações que fiz no arquivo. dai agora sim, vou fazer um novo commit com as alterações que desejo.

git status

git reset --soft HEAD~1
vou dar o reset pra voltar para o útimo commit, mas vou dar o soft para não apagar as modificações.
ou seja vou voltar um commit mas sem apagar as modificações (soft)

***************************************************************************************************************
## DELETAR COMMITS E AS MODIFICAÇÕES NOS ARQUIVOS

git status

git reset --hard <codigo do commit>

obs AÇÃO DESTRUTIVA!!! 

exemplo
git status
git reset --hard HEAD~1
vai destruir o ultimo commit e vai voltar para o penultimo commit

obs interessante é que nos comandos acima, ele mexe no stage e no commit, mas não mexe com o que já esta salvo
la no github.

### SE QUISER TRAZER TUDO QUE ESTA NO GITHUB PARA O SEU COMPUTADOR NOVAMENTE

git pull origin main
esse comando busca os arquivos que já estão salvos no github.
*********************************************************************************************
## COMO ATUALIZAR O REPOSITÓRIO LOCAL EM RELAÇÃO AO REPOSITÓRIO REMOTO

git status

git pull <nome remoto> <nome da branch>

exemplo
git pull origin main
com esse comando ele vai trazer o que esta no remoto para o local
obs quando tem um histórico um pouco maior no github do que o local, então só fazer esse comando

***********************************************************************************************
## COMO RESOLVER UM PUSH REJEITADO
### É UM PROBLEMA COMUM
### NÃO É PERMITIDO ENVIAR UM PUSH SE O SEU REPOSITÓRIO LOCAL ESTA ATRASADO EM RELAÇÃO AO REMOTO
### O QUE FAZER? TENHO QUE ATUALIZAR O REPOSITÓRIO LOCAL 

git status

git log --online
vai mostrar todos os commits do projeto

git pull <nome do remoto> <nome do branch>
vai buscar no repositório e trazer para o local

exemplo
git pull origin main
pode ser que abra o vim, o editor do linux. porque eu tentei fazer um commit, só que tem arquivos a mais lá no remoto
ESC
:wq
comando acima vai sair do modo edição do vim, e vai salvar o merge que é uma juntada

git log --online
aparece a ordem que foi feitos os commits e como agora eu estou repeitando a ordem...

git push 
agora ele vai fazer o push para o remoto

obs nesse exemplo acima, o merge é o 'mesclar' os 2 commits, ou seja juntou o commit remoto com o commit local
*************************************************************************************************************
## RESOLVENDO CONFLITO
##  





























