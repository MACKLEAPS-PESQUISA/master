# Master
Repositório guia para os membros do **MackLeaps**. 

O desenvolvido dos projetos relacionados ao MackLeabs será centralizado dentro deste repositório.

Antes de iniciar qualquer projeto e ou reposítório dentro desta organização uma [**Issue**](https://github.com/MACKLEAPS/master/issues) deve ser reportada antes, acompanhada da ATA da reunião que deu origem ao projeto ou uma simples justificativa para tal. É de interesse organizacional a documentação dos projetos realizados por este laboratório, então acompanhado ao **Issue** deve ser criada também, a medida da necessidade, uma página nesta [**Wiki**](https://github.com/MACKLEAPS/master/wiki) especificando o trabalho que será realizado ou a lógica por de trás desse trabalho. 

A **Issue** deve ser reportada dentro desse repositório e preferencialmente linkando sua página na Wiki, como também os membros envolvidos. Se houver a necessidade de criar uma equipe (Team) para a realização do projeto em questão, a equipe deverá ser citada. 

O andamento do projeto será supervisionado através dessa **Issue**, ou seja, qualquer dúvida, observação ou simples reporte deverão acontecer através do sistema de Issues. **Para casos onde o assunto em questão é técnico demais, reportá-lo de maneira branda em sua issue de origem e linká-lo com sua issue dentro do repositório.**

Em resumo, 

* Outros repositórios só poderão ser criados com base nas Issues reportadas neste repositório. Ou seja, este repositório funcionará como um catálogo dos projetos realizados pela organização MackLeaps. 

* A Wiki servirá como parte da documentação dos projetos organizados por este repositório. 


### Regras gerais para utilização dos repositórios GitHub. 

### Issues

Qualquer tarefa ou problema deve ser reportado como uma Issue **antes** de executar qualquer coisa, seja a realização de
uma tarefa, ou a correção de um problema.

Além disso, um desenvolvedor somente poderá trabalhar na Issue quando ela for classificada (bug, enhancement, etc) e/ou
comentada pelo proprietário ou algum administrador do repositório.

### Wiki

Qualquer alteração na Wiki somente será feita depois de uma Issue específica para isso (veja item anterior) e de sua
discussão/explicação por meio dos comentários da própria Issue. 

### Git & Branches

O correto uso de git é fundamental. Assim, evitando problemas futuros, as branches `master` e `dev` estão bloqueadas
para `push` e somente serão atualizadas por meio de `pull requests`. Estes serão inspecionados **por todos** os
desenvolvedores e, caso algum problema seja encontrado, deverá ser corrigido antes de ser aceito - isso será feito tanto
nos comentários das issues quanto nos pull-request.

Assim, utilizaremos [No Switch Yard (NoSY)](http://geant.cern.ch/content/suggested-work-flow-distributed-projects-nosy)
como workflow, além de usar um [Git Branch Model](http://nvie.com/posts/a-successful-git-branching-model/) específico
para criação de `branches` e `pull requests`.

Para facilitar um pouco esse entendimento, segue um **exemplo prático** de uso no NoSY e do Git Branch Model (com
algumas padronização de nomes):

* Faça a sua `branch` a partir da `dev`, substituindo **##** pelo número da issue que foi documentada (com o hífen).

```bash
$ git checkout -b [issue-##] remotes/origin/dev
```

* A partir de então, faça as alterações e sempre realize `commit` para marcar a evolução da correção.

```bash
$ git add # arquivos
$ git commit # com os seus commits
```

Lembre-se que um `commit` pode abranger mais de um arquivo, portanto adicione quantos arquivos forem necessários para
caracterizar o seu `commit`.

* Uma vez finalizada as alterações, sincronize sua `branch` com a `dev`.

```bash
$ git checkout dev
$ git pull
$ git checkout [issue-##]
$ git rebase origin/dev
```

* Se não tiver conflitos, envie suas alterações para o repositório.

```bash
$ git push origin HEAD
```

A patir desse momento, a sua nova branch deve aparecer no repositório.

* Aguarde o build e demais hooks avaliarem a `branch`. Caso nenhuma falha seja encontrada, faça um `pull-request` da
  `branch-##` para a `dev` e aguarde os comentários da revisão - alguns hooks farão comentários automáticos neste
  `pull-request` e, portanto, as anotações deverão ser corrigidas e/ou explicadas.

* Caso seja necessário alterar a sua `branch` devido a alguma falha do build, dos hooks, ou dos comentários de revisão,
  faça-os normalmente na sua branch `issue-##`, sincronizando-a novamente ao final das mudanças e reenviando-a para o
  repositório. Aguarde os resultados descritos no passo anterior e, se for o caso, repita todo este processo. Se um
  pull-request já foi feito, não é necessário refazê-lo ou fechá-lo.

```bash
$ git checkout [issue-##]
$ git add # arquivos
$ git commit # com os seus commits
$ git rebase origin/dev
$ git push --force origin HEAD
```

A primeira linha de uma mensagem de `commit` deve ser simples, precisa e significativa e, se possível, conter no máximo
50 caracteres. Se for necessária uma mansagem maior, resuma o problema corrigido na **1a linha** e a partir da **3a
linha** (_terceira linha_) da mensagem explique com mais detalhes o `commit`, mantendo 120 caracteres por linha. Quando
pertinente e possível, utilize [auto-referências](https://help.github.com/articles/autolinked-references-and-urls/) às
issues e desenvolvedores, e mensagens com
[palavras-chaves](https://help.github.com/articles/closing-issues-via-commit-messages/).

Material para estudos retirado [do repositório do Professor Calebe](https://github.com/Prof-Calebe/substituicao/blob/master/README.md).

### Simples comandos para o GitHub

* Criação de hyperlinks:
  ``` [Referência](Link-De-Referência)
  ```
  


