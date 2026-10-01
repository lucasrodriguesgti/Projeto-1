# Ciclo de Vida de um Projeto no GitHub

## Introdução

O GitHub é uma plataforma que permite armazenar projetos na nuvem,
acompanhar alterações e colaborar com outras pessoas. Para utilizá-lo, é
importante compreender como criar um repositório, enviar os arquivos,
documentar o projeto e manter o código atualizado.

Neste documento, apresento as principais etapas do ciclo de vida de um
projeto no GitHub, desde a criação até as atualizações.

------------------------------------------------------------------------

# 1. O Passo a Passo da Criação e Envio

## 1.1. Criando um repositório no GitHub

De início a opção é entrar Github e acessar sua conta.
Logo na tela inicial, você irá clicar no ícone “+” na parte superior direita do github. Lá encontrará a opção de novo repositório.
Clique e aparecerá informações para adicionar, como título do repositório, descrição e o tipo de configuração, entre elas, privado ou público, tipo de inicialização na qual usamos readme. Após, clique em criar repositório.


Durante a criação, preencho as informações iniciais:

-   **Repository name (nome):** escolho um nome que identifique o
    projeto.
-   **Description (descrição):** escrevo, de forma breve, qual é o
    objetivo do projeto.
-   **Visibilidade:** seleciono *Public* se o projeto puder ser visto
    por qualquer pessoa ou *Private* se quiser restringir o acesso.
-   **README:** posso marcar a opção para criar um arquivo README.md
    inicial.
-   **.gitignore:** posso escolher um modelo adequado à linguagem
    utilizada, para evitar o envio de arquivos desnecessários.
-   **License (licença):** posso selecionar uma licença que indique como
    outras pessoas podem utilizar o projeto.

Depois de conferir as opções, clico em **Create repository**. Assim, o
repositório é criado no GitHub e fica disponível na nuvem.

## 1.2. Conectando a pasta local ao repositório remoto

A conexão é essencial criar uma pasta de projetos para armazenar todo conteúdo/arquivo produzido.

Se a pasta ainda não utiliza Git, inicio o controle de versão com:

``` bash
git init
```

Esse comando transforma a pasta em um repositório Git local. Depois,
adiciono o endereço do repositório criado no GitHub como repositório
remoto:

``` bash
git remote add origin https://github.com/USUARIO/NOME-DO-REPOSITORIO.git
```

Substituo `USUARIO` e `NOME-DO-REPOSITORIO` pelos dados reais do meu
repositório. O nome `origin` é um apelido convencional para identificar
o endereço remoto.

Para conferir se a conexão foi configurada, utilizo:

``` bash
git remote -v
```

Esse comando mostra os endereços remotos associados ao projeto.

> Se eu ainda não tiver uma pasta com arquivos e preferir baixar o
> repositório já criado, também posso utilizar
> `git clone URL_DO_REPOSITORIO`. Nesse caso, o Git cria uma cópia local
> já conectada ao remoto.

## 1.3. Fazendo o primeiro envio dos arquivos

Depois de colocar os arquivos do projeto na pasta local, sigo a
sequência abaixo:

**1. Verificar o estado do projeto**

``` bash
git status
```

O comando informa quais arquivos são novos, foram modificados ou estão
preparados para o próximo commit.

**2. Preparar os arquivos para o commit**

``` bash
git add .
```

O ponto indica que desejo preparar as alterações da pasta atual. Posso
também adicionar um arquivo específico, por exemplo,
`git add README.md`.

**3. Registrar as alterações**

``` bash
git commit -m "Primeiro commit do projeto"
```

O commit cria um registro das alterações preparadas. A mensagem deve
resumir o que foi feito.

**4. Definir a branch principal, se necessário**

``` bash
git branch -M main
```

Esse comando renomeia a branch atual para `main`, nome bastante
utilizado como branch principal.

**5. Enviar os arquivos ao GitHub**

``` bash
git push -u origin main
```

O `push` envia os commits locais para o repositório remoto. A opção `-u`
configura o vínculo entre a branch local `main` e a branch remota
correspondente, facilitando os próximos envios.

Após o envio, acesso a página do repositório no GitHub e atualizo a
página para conferir se os arquivos foram publicados.

------------------------------------------------------------------------

# 2. A Anatomia do README Perfeito

## 2.1. Para que serve o README?

O arquivo **README.md** é a apresentação e o guia inicial de um projeto.
Ele explica o que o projeto faz, qual problema procura resolver e como
uma pessoa pode utilizá-lo.

Seu público pode incluir outros desenvolvedores, professores, colegas de
equipe, recrutadores e qualquer pessoa que visite o repositório. Um
README bem organizado ajuda essas pessoas a entender o projeto sem
precisar analisar todo o código.

## 2.2. Informações essenciais de um README profissional

Um README pode variar conforme o tamanho e a finalidade do projeto, mas
algumas informações são especialmente úteis:

1.  **Título:** identifica o projeto de maneira clara e objetiva. Deve
    permitir que o leitor reconheça rapidamente o conteúdo do
    repositório.

2.  **Descrição:** apresenta o objetivo do projeto, o problema que ele
    procura resolver e, quando necessário, suas principais
    funcionalidades.

3.  **Tecnologias utilizadas:** informa as linguagens, ferramentas,
    bibliotecas e frameworks empregados. Isso ajuda a entender os
    requisitos e o ambiente do projeto.

4.  **Instalação e execução:** explica o que é necessário para preparar
    e executar o projeto. Pode incluir comandos, dependências e
    configurações iniciais, permitindo que outra pessoa reproduza o
    procedimento.

5.  **Como utilizar:** descreve como acessar as funcionalidades ou
    utilizar o programa depois de instalado. Exemplos de uso podem
    tornar as instruções mais claras.

8.  **Autor e contribuições:** identifica quem desenvolveu o projeto e,
    quando aplicável, explica como outras pessoas podem contribuir.

Nem todo projeto precisa apresentar todas essas seções com o mesmo nível
de detalhe. O conteúdo deve ser adequado à finalidade do repositório e
manter as informações atualizadas.

## 2.3. O poder do Markdown

O **Markdown** é uma linguagem de marcação simples, utilizada para
formatar textos sem exigir ferramentas complexas. No GitHub, o arquivo
README normalmente utiliza a extensão `.md`, e a plataforma converte a
marcação em uma página organizada e fácil de ler.

Alguns recursos comuns são:

-   `# Título` para criar um título principal.
-   `## Subtítulo` para organizar seções.
-   `**texto**` para destacar palavras em negrito.
-   `*texto*` para aplicar itálico.
-   `- item` para criar listas.
-   `` `comando` `` para destacar comandos e trechos curtos de código.
-   Blocos de código para apresentar exemplos completos.

O Markdown facilita a leitura porque separa o conteúdo em títulos,
parágrafos, listas e exemplos. Além disso, o arquivo continua sendo
texto simples, fácil de editar em diferentes editores e de acompanhar
pelo Git. Dessa forma, consigo documentar o projeto de maneira clara sem
precisar criar uma página web do zero.

------------------------------------------------------------------------

# 3. O Mapa das Atualizações (Commits e Pushes)

Depois que o projeto está no GitHub, é comum realizar correções,
adicionar funcionalidades e atualizar a documentação. Existem diferentes
formas de registrar e enviar essas mudanças.

## 3.1. GitHub Online

Pelo navegador, posso abrir um arquivo no repositório e clicar no ícone
de edição, geralmente representado por um lápis. Depois de alterar o
conteúdo, escrevo uma mensagem que explique a mudança e confirmo a
edição por meio de um commit.

Essa opção é útil para pequenas alterações, como corrigir um erro de
digitação no README, atualizar uma informação ou editar um arquivo
simples.

Sua principal limitação é que não oferece a mesma praticidade para
mudanças grandes ou que envolvam vários arquivos. Também não substitui
um ambiente local completo para executar e testar o programa antes de
publicar as alterações.

## 3.2. Git via linha de comando (Terminal)

No terminal, utilizo os comandos do Git para acompanhar, preparar,
registrar e enviar as alterações. Um fluxo comum é:

``` bash
git status
git add .
git commit -m "Descreve a alteração"
git push
```

-   `git status`: verifica quais arquivos foram alterados.
-   `git add`: seleciona as mudanças que farão parte do próximo commit.
-   `git commit`: registra as mudanças selecionadas no histórico local.
-   `git push`: envia os commits para o repositório remoto.

Essa é uma forma tradicional de trabalhar porque o Git foi desenvolvido
para ser utilizado por comandos e permite controlar com precisão as
operações. Também é muito útil para automatizar tarefas e trabalhar em
diferentes ambientes. Para utilizá-lo, é necessário conhecer os comandos
e entender o estado do repositório.

Antes de enviar alterações, também posso usar `git pull` para buscar e
integrar mudanças do repositório remoto, evitando trabalhar com uma
versão desatualizada. Se houver conflitos, preciso resolvê-los antes de
concluir a integração.

## 3.3. IDEs, como o Visual Studio Code

O Visual Studio Code possui uma área chamada **Controle do
Código-Fonte**, que permite utilizar o Git por meio de uma interface
gráfica.

Nela, consigo visualizar os arquivos modificados, abrir as diferenças
entre a versão anterior e a atual, selecionar quais alterações quero
incluir e escrever a mensagem do commit. Depois, posso utilizar as
opções de sincronização ou de envio para publicar os commits no GitHub,
conforme a configuração do projeto.

A interface facilita a visualização das mudanças e reduz a necessidade
de memorizar todos os comandos. Ainda assim, é importante compreender o
que são commit, branch, pull e push, pois a ferramenta apenas oferece
uma maneira visual de executar essas operações.

## 3.4. GitHub Desktop

O **GitHub Desktop** é um aplicativo que permite gerenciar repositórios
Git por meio de uma interface gráfica. Após conectar minha conta e
adicionar ou clonar um repositório, consigo visualizar as alterações
feitas nos arquivos.

O aplicativo permite:

-   Conferir quais arquivos foram modificados.
-   Visualizar as diferenças entre versões.
-   Escrever uma mensagem e criar um commit.
-   Enviar commits ao GitHub por meio do *push*.
-   Buscar atualizações do repositório remoto por meio do *fetch* ou
    *pull*.
-   Trabalhar com branches e acompanhar o histórico de alterações.

Essa ferramenta torna o processo mais visual, pois apresenta as mudanças
antes de registrá-las. Pode ser especialmente útil para quem está
começando a aprender Git. Mesmo utilizando o aplicativo, é importante
entender o significado das operações para evitar enviar alterações
incorretas.

## 3.5. A filosofia da atualização contínua

Manter o repositório atualizado, realizando commits pequenos e
frequentes, ajuda a organizar o desenvolvimento. Cada commit pode
representar uma alteração específica, como corrigir um erro, adicionar
uma funcionalidade ou atualizar a documentação.

Esse hábito oferece algumas vantagens:

-   **Histórico organizado:** facilita entender o que foi alterado e em
    qual momento.
-   **Rastreamento de erros:** ajuda a identificar em qual alteração um
    problema pode ter surgido.
-   **Recuperação:** permite consultar versões anteriores e, quando
    necessário, reverter mudanças.
-   **Colaboração:** facilita a integração do trabalho de diferentes
    pessoas.
-   **Acompanhamento:** mantém o repositório alinhado com a evolução
    real do projeto.

Enviar tudo apenas no final do mês pode dificultar a identificação de
erros, tornar o histórico confuso e aumentar o risco de perder
alterações. Por isso, procuro dividir o trabalho em partes menores,
registrar cada etapa concluída com uma mensagem clara e enviar as
mudanças regularmente.

------------------------------------------------------------------------

## Conclusão

O ciclo de vida de um projeto no GitHub envolve criar um repositório,
conectar o ambiente local, registrar e enviar arquivos, documentar o
projeto e manter as alterações atualizadas. O README facilita a
compreensão do trabalho, enquanto os commits preservam o histórico e os
pushes sincronizam as mudanças com a nuvem.

Compreender as opções de atualização --- pelo navegador, terminal, VS
Code ou GitHub Desktop --- permite escolher o método adequado para cada
situação e manter o projeto organizado durante seu desenvolvimento.
