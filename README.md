# Git Basics

## Tutorial básico dos principais procedimentos com Git.

A seguir teremos um exercício de clonagem e modificação de um repositório Git, faremos este procedimento em sala de aula de forma coletiva e que pode ser replicado em outros no qual você seja um contribuidor.

### Sigam o passos abaixo com atenção

#### **1 -** Se você ainda não tem uma conta no GitHub, crie uma em https://github.com/ ;

#### **2 -** Preencha o formulário com os dados necessários no link a seguir: https://goo.gl/forms/3mV24SCu1VsYfGLX2 ;

#### **3 -** Acesse o seu terminal nativo (Linux/Unix/macOS) ou o Git Bash (Windows) e navegue até o diretório/pasta onde ficará armazenado este repositório do GitHub ;

#### **4 -** Faça a clonagem deste repositório com o comando `git clone 'https://github.com/andrewpotterdr/gitbasic'` ;

#### **5 -** Entre na pasta `gitbasic` criada com a clonagem do repositório e execute o comando `git branch` ;
O comando acima irá listar os branches existentes neste repositório, não é uma boa prática mexer diretamente no branch `master`, especialmente quando há mais de um contribuinte, por isso para modificações no conteúdo do repositório são criadas novos branches como veremos a seguir.

#### **6 -** A seguir você deve criar um branch com o seu nome com o comando `git branch` seguido de seu nome. Exemplo: `git branch michael` ;
Ao executar o comando acima, você estará criando um novo branch no qual poderá editar sem que mude o que há no branch original que no caso é o branch `master`.

#### **7 -** Execute o comando `git branch` novamente para listar os branches existentes ;
Note que ao executar o comando acima aparece alguns branches, inclusive o branch com o seu nome, no entanto perceba que você ainda não saiu do branch `master`, na lista, o branch em qual você está é indicado com um asterisco antes do nome do branch. Exemplo `* master`. A seguir vamos descobrir como sair de um branch para outro.

#### **8 -** Execute o comando `git checkout` seguido de seu nome, seguindo a mesma ideia do passo Nº 6. Exemplo `git checkout michael` ;
O comando `git checkout` seguido do nome de um branch, faz com que você saia do branch corrente e entre no branch de destino especificado no comando.

#### **9 -** Uma vez estando dentro do branch de seu nome, crie um arquivo com seu nome com a extensão `.txt`. Exemplo: `touch michael.txt` ;
Uma vez estando fora do branch `master` você poderá editar, adicionar arquivos da forma que achar melhor e se algo correr errado, poderá apagar esse branch, criar um outro branch e começar novamente.

#### **10 -** Execute o comando `git status` ;
O comando acima irá lhe indicar quais arquivos foram modificados e ainda não foram postadas as modificações referentes a ele. Note que esses arquivos se apresentarão na tela em cor vermelha (ao menos é o mais comum).

#### **11 -** Adicione os arquivos editados com o comando `git add` seguido pelo nome do arquivo que foi editado e cujas modificações ainda não foram postadas (mostrado pelo comando `git status` executados anteriormente). Exemplo: `git add michael.txt` ;
É importante que você divida as postagens por seção ou por assunto específico. Por exemplo, se em seu projeto houver duas aplicações diferentes, é recomendável postar as modificações referentes a cada aplicação em momentos diferentes. Com o comando `git add` você vai especificar o que será postado naquele momento, uma dica é que se você quiser postar as modificações feitas num diretório você pode executar o comando `git add` seguido pelo nome do diretório, se você quiser postar todas as modificações do seu diretório corrente você pode executar o comando `git add .`.

#### **12 -** Após executar o comando `git add` como mostrado acima, execute novamente o comando `git status` para checar o status do branch no geral. Note que os arquivos selecionados no comando `git add` agora são mostrados em verde (ao menos é o mais comum), faltando apenas fazer a postagem das modificações, ou seja, o commit, o que faremos no próximo passo ;

#### **13 -** Após realizadas as modificações e selecionados os arquivos os quais as modificações serão postadas no momento (seguindo o comando anterior), é hora de postar de fato as modificações dentro de seu branch, executando o comando `git commit` ;
Ao executar esse comando, abrirá um editor de texto (nano ou vim, dependendo de seu padrão de instalação), onde você deverá descrever as modificações feitas nessa porção do projeto que estará sendo postada. Um detalhe é que, ao exeuctar o comando `git commit` você postará as informações dentro do branch, mas esse só será visível no site por exemplo, quando você fizer a integração com o o branch que será enviado de volta ao site, que no caso é o branch original, que nesse caso é o branch `master` e é o que faremos nos próximos passos.

#### **14 -** Após realizada a postagem das modificações selecionadas por meio do comando `git commit` executado no passo anterior, execute novamente o comando `git status`, se este mostrar que não há mais nada para ser realizado commit, e não há mais nada que queira modificar, chegou a hora de integrar o seu branch com o branch `master` que é o que faremos a seguir ;

#### **15 -** Uma vez realizadas e postadas as modificações necessárias, é hora de juntar esse branch com o branch `master` e tornar as modificações definitivas ;
Essa é uma parte importante na qual você deve tomar bastante cuidado, procure por erros e certifique-se de não deixá-los no branch (a não ser que você tenha combinado com outros contribuidores para analisar o erro e tentar corrigí-lo, ou qualquer motivo mais específico) pois esse branch irá para o branch `master` o qual será acessado por outro contribuidor do projeto.

#### **16 -** O primeiro passo para integrar o seu branch ao branch master é mudar de branch de volta para o branch master com o comando `git checkout master` ;
Após executar esse comando, execute novamente o comando `git branch` para se certificar que você realmente está no branch master como indicado pelo asterisco.

#### **17 -** Após executado o passo anterior, executar o comando `git merge` seguido de seu nome que no caso é o nome do branch no qual você fez as modificações. Exemplo `git merge michael` ;
Ao executar esse comando execute novamente o comando `git status` e note que ele indicará que o branch master está x commits a frente do branch 'origin/master' (que é o branch que está online). E agora chegamos ao momento em que outras pessoas poderão ver e acessar as modificações que você fez no projeto enquanto estava apenas em seu computador.

#### **18 -** Para postar online todas as modificações postadas dentro do branch master em sua máquina, execute o comando `git push origin master`, será pedido que você digite seu e-mail ou nome de usuário e senha do GitHub para prosseguir a publicação e pronto, seu trabalho foi publicado e está online para todos que tiverem acesso ;
Um detalhe que pode ocorrer é que um outro contribuidor desse projeto tenha modificado algumas coisas e postado antes que você tivesse baixado a última versão do repositório, para corrigir isso e adquirir a versão mais recente do repositório, execute o comando `git pull origin master` que vai fazer o download das modificações feitas naquele repositório, se você tem modificações ainda a serem publicadas, abrirá novamente um editor de texto para que você descreva os detalhes da junção do seu branch master atual com o branch master que está sendo baixado com o comando `git pull`. Salve o arquivo e após isso execute novamente o comando `git push origin master`.

## Alguns detalhes

É sempre importante ter uma divisão bem definida da execução das tarefas num projeto para que não haja conflitos de terem modificado o mesmo arquivo e postar as modificações dele no git. Se isso for inevitável ou se por acaso acontecer não se apavore, há uma solução pra solução de conflitos por meio da ferramenta `meld` -> http://meldmerge.org/ ;

O GitHub faz o versionamento de projeto e acordo com os commits então não se apavore se a versão atual de seu projeto não estiver funcionando por algum motivo que você desconhece, você sempre pode voltar para versões anteriores onde tudo esteja funcionando corretamente (se houver essa versão), e a partir daí poderá identificar o que foi adicionado para que houvesse determinados erros ou simplesmente recomeçar a fazer uma funcionalidade partindo da versão mais antiga do código ;

Sempre antes de começar a remover, adicionar ou alterar partes no repositório, é importante ter baixada a versão mais atualizada do repositório que está online. Para isto antes de integrar um branch criado por você com o branch `master` por meio do comando gir merge, é importante que você baixe a versão mais atualizada do master com o comando `git pull origin master` e somente após esse comando usar o `git merge` para depois usar o `git push` ;

Para remover ou mover arquivos já existentes no repositório que você vai clonar ou baixar a versão mais nova, é necessário usar os comandos `git mv`e `git rm` pois o git identificará que terá que ser mudado nos repositórios e salvo no commit também se assim indicado.
