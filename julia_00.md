# Computação básica para física - Guia de Início
Nesse capítulo vamos discorrer brevemente sobre os conhecimentos mínimos e instalação necessária para executar programas em Julia. Alguns programas de exemplo estarão dispostos nesse capítulo, o que não significa que seja necessário entender o que eles fazem por enquanto.

## Para quem?

Esse material __está sendo desenvolvido__ tendo em mente alunos de graduação do curso de física que buscam começar a sua jornada no mundo da computação científica. Seja para realizar cálculos numéricos, plotar gráficos, desenvolver inteligências artificiais para resolver os mais diversos problemas ou simplesmente automatizar tarefas chatas e repetitivas. O que é exatamente o que a programação mais serve. 

Esse material pode ser utilizado como consulta, revisão ou até mesmo como recomendação de programadores experientes para seus alunos ou colegas que pretendem aprender mais. Críticas e recomendações são bem vindas, tanto no próprio github, através dos _issues_, como também no meu email acadêmico em `arthur.pasqualotto@acad.ufsm.br`. 

## Como estudar?

Esse material foi pensado para ser lido ao mesmo tempo que se executa os comandos simples no terminal ou no REPL, mas o que são? Por enquanto o terminal pode ser entendido como uma forma de se comunicar com o computador utilizando apenas o teclado. O REPL é uma espécie de "terminal de Julia" para executar linhas de código "na hora". Veremos mais sobre essas coisas mais tarde, por enquanto alguns outros conceitos introdutórios serão apresentados.

Programação é difícil. Eu estaria sendo completamente desonesto se falasse que programar é algo extremamente simples. Programar exige pensar de formas diferentes, de formas novas, sobre o mesmo problema que se busca resolver. Ser programador também é sobre se contrar frequentemente com tentaivas frustradas de realizar uma tarefa, para só depois de muito tempo e trabalho você perceber que fez alguma coisa muito errada e uma boa parte do seu progresso na verdade pode ter sido em vão. Eu digo que "pode ter sido" porque muitas vezes é, mas na maioria das vezes não, a falha é amiga do aprendizado. Mas pode ser sim muito frustrante.


A frustração que encontramos ao aprender a programar é comparável à frustração que temos quando estudamos matemática. Isso não é uma novidade, tendo em vista que a computação foi desenvolvida por matemáticos. Ao estudar esse material ou qualquer material sobre programação você vai encontrar de forma inevitável símbolos, comandos, linhas de código e outras coisas que você não vai entender absolutamente NADA. Embora seja um pouco chato e até amedrontador no início isso é necessário. É necessário nos expormos e confrontarmos com a nossa ignorância se queremos aprender algo novo. Um dos principais motivos pelos quais eu comecei a desenvolver esse material é exatamente diminuir o sofrimento dos estudantes de programação de "primeira viagem". Para isso alguns conceitos fundamentais devem ser expostos antes de começarmos a falar sobre computação de fato. 

# Hardware e Software
O computador é composto pelas suas peças eletrônicas, como chips, placas, unidades de armazenamento, de memória de acesso aleatório e unidades de processamento. As peças físicas que compõem o computador são chamadas de "Hardware". A memória RAM (_Random Access Memory_), o HD (_HDD: Hard Disc Drive_), o SSD (_Solid State Drive_), a Placa mãe e o processador são exemplos de _Hardware_. 
O computador também é composto pelos arquivos e programas que são utilizados para realizar e organizar as diferentes tarefas que serão executadas. Os programas e arquivos necessários para o funcionamento do computador para as diferentes tarefas que serão executadas são chamados de "Software". 

Uma linguagem de programação, como `Julia Language`, é utilizada para desenvolver software. Esse é um material introdutório, com o intuito de trazer os conceitos necessários para que possa se aprender, _do zero_, a desenvolver _softwares_ simples com enfoque em computação científica.

#  O que é o terminal/CLI?
O _terminal de texto_ é uma CLI, _command-line interface_, ou "Interface de linha de comando". Através da qual podemos interagir com o computador utilizando comandos de texto. O terminal padrão das distribuições de linux (sistema operacional de código aberto e de uso livre) e do sistema mac (sistema privado da Apple) é o bash. O Windows (sistema privado da Microsoft) possui o CMD (_Command Prompt_) ou "Prompt de Comando". Todos esses programas podem ser entendidos de forma grosseira como "pequenas janelinhas pretas" com as quais executamos programas e acessamos pastas.
### Qual é o melhor sistema operacional?
Como existem diferentes tipos diferentes de sistemas operacionais, com diferentes funcionalidades, públicos alvo, curvas de aprendizado e outras características específicas, surge naturalmente a dúvida sobre qual seria o melhor para se utilizar. 
Essa é mais uma dúvida que não possui resposta objetiva, ou melhor, é uma pergunta feita pela. 
Diferentes usuários vão ter necessidades e habilidades diferentes. 
Algumas pessoas não precisam de mais que um navegador de arquivos, um editor de texto e um navegador de internet para conseguir realizar todas as tarefas que precisa. 
Na verdade apenas o navegador pode ser mais que suficiente para a gigantesca maioria das pessoas. 
Mas instalar e executar os softwares em seu próprio computador é uma habilidade necessária para a maioria dos pesquisadores e cientistas que estão desenvolvendo e compartilhando dados e programas entre seus colaboradores, colegas e alunos, para resolver os mais diversos problemas. 

Portanto a escolha do melhor sistema operacional é uma questão pessoal, subjetiva e de contexto. 
Se "Qual é o melhor sistema operacional?" é uma "meia pergunta" eu acredito que a pergunta inteira seja "Qual é o melhor sistema operacional para mim?". A resposta para essa pergunta é "Aquele que melhor se encaixa nas suas necessidades e no seu estilo de trabalho". 
Tal resposta pode variar de pessoa para pessoa, de situação e do tempo. 

Eu já utilizei Windows, Linux e Mac preferencialmente em diversos contextos, embora considere o Linux superior eu tenho conseguido trabalhar melhor utilizando um sistema Windows com WSL (_Windows Subsistem for Linux_), ou "Subsistema Windows para Linux", onde uma distribuição do Linux é executada pelo Windows.
Então, de forma simples e básica, a minha resposta para essa pergunta vai ser simples e direta.

"Qual é o melhor sistema operacional para mim?"

Aquele que você conseguir trabalhar.

Realizar as tarefas que você precisa fazer, sofrendo menos, tendo menor dificuldade em executá-las ou tendo maior prazer em realizá-las. Isso vai fazer uma diferença enorme no longo prazo. Programação é sobre tornar coisas chatas e repetitivas em tarefas que você precisa fazer o mínimo de vezes possível. 


### Arquivos, pastas e caminhos
Os comandos utilizados pelo terminal do linux e do mac são escritos utilizando a linguagem `bash`, uma linguagem de comando utilizada para executar as operações no terminal. Dessa forma quando nos referirmos ao terminal bash estaremos nos referindo genericamente aos dois sistemas, a menos que especificado.
A linguagem utilizada pelo CMD do Windows é uma linguagem a parte, porém alguns comandos são similares - realizam a mesma função, ou quase - porém escritos de outra forma - possuem sintaxe diferente. A estrutura de pastas dos sistemas são diferentes mas a forma de navegar pelos arquivos é a mesma. 
#### Usando o Bash
Abrindo o terminal em uma pasta, ou folder, de exemplo, chamado `exemplo`, podemos escrever `ls` na linha de comando e apertar a tecla "enter" para executar. O comando `ls` mostra uma lista de todos os arquivos e diretórios de uma pasta, ao escrever apenas 
```bash
ls
# ou 
ls .
```
vamos listar todos os arquivos e diretórios da pasta atual. Podemos sempre nos referir à pasta atual como `.` mas isso não é necessário na maioria das vezes. Podemos nos referir à pasta superior utilizando dessa forma executando o comando
```bash
ls ..
```
podemos ver listados os arquivos da pasta cuja a pasta atual está dentro. 
No CMD o comando similar é o `dir`. Sendo os últimos comandos como 
```cmd
dir
dir .
dir ..
```
Para saber qual é a pasta atual que o terminal está localizado podemos executar
```bash
pwd
```
para `print work directory`, ou, "imprima o diretório de trabalho". 
Podemos criar uma pasta utilizando o comando 
```bash 
mkdir nome_da_pasta
```
Podemos executar o comando `ls` novamente para verificar se a pasta foi realmente criada, apenas para ter certeza. Após isso podemos acessar a pasta criada utilizando o comando `cd`, para "change directory" ou "mudar de diretório"
```bash
cd nome_da_pasta
```
para voltar à pasta do usuário podemos apenas executar o comando `cd`. Para ir da pasta atual para a pasta superior podemos executar o comando
```bash 
cd ..
```
Ou para ir para uma pasta qualquer podemos executar o comando `cd` seguido pelo endereço ou caminho da pasta que desejamos acessar com o terminal 
```bash 
cd /home/usuario/documentos/pasta
```
Em todos os sistemas temos o diretório raiz, ou `root directory`, que é representado por uma barra `/` nos sistemas linux e mac e por uma contrabarra `\`nos sistemas windows. As barras e contrabarras também são utilizadas para separar uma pasta da outra na descrição de um caminho.  
### Editando arquivos no terminal 
Podemos criar e editar arquivos diretamente do terminal bash,, por exemplo, que já possui o programa chamado `vi` para edição de texto diretamente do terminal. Outros programas de edição de texto no terminal existem, como o `vim` ou o `neovim`. Porém sua utilização é razoavelmente complexa e eu pessoalmente acho desnecessário a sua utilização por estudantes de nível introdutório. Porém pelo fato de serem muito utilizados por desenvolvedores avançados merecem essa menção honrosa.
# Editores de texto e IDE
Teoricamente tudo que precisamos para utilizar um programador para começar a programar é de um terminal. Através dele podemos navegar e criar pastas, criar e editar arquivos e executá-los. 
Editores de texto são programas que foram criados com o intuito de melhorar a experiência de escrita para documentos de texto, incluindo programas de computador de diversas linguagens. Editores de texto voltados para programação ou desenvolvimento de software podem ser simples como qualquer bloco de notas ou avançado com diferentes configurações. O importante mesmo é conseguir encontrar o ambiente que favoreça o seu fluxo de trabalho. Existem ambientes integrados de desenvolvimento, ou _Integrated Developlment Environments_, que permitem escrever e executar os programas no mesmo lugar com pouco esforço. O exemplo principal de _IDE_ para o desenvolvimento de programas em Julia Language é o _Visual Studio Code_ ou _VSCode_. Esse IDE também é que eu pessoalmente recomendo para iniciantes em Julia devido aos seus plugins que facilitam o fluxo inicial de trabalho.
## Escrevendo programas 
Programar é uma tarefa complexa. Como toda tarefa complexa, podemos torná-la mais simples de se resolver cultivando habilidades e práticas de desenvolvimento que se encaixe melhor nas nossas necessidades. Dentre essas habilidades, para a computação científica, podemos destacar as seguintes:
- Abstração:
	É extremamente necessário exercitar a capacidade de pensar em um problema de diversas formas possíveis. Como podemos interpretar e reimaginar o mesmo problema para que ele possa ser resolvido de uma forma mais eficiente ou mais fácil de se compreender é uma das habilidades mais importantes não só na programação, mas na ciência como um todo;
- Organização e Transparência: 
	O seu programa vai ser utilizado por você, para resolver um problema específico em um determinado momento. Ele pode ser reutilizado por você, quando esse mesmo problema surgir novamente. Ele também pode ser reutilizado por você para resolver um problema similar, servindo de base para um novo programa. Por isso é importante manter o programa organizado, salvo em um local seguro, e escrito de forma que seja fácil continuar trabalhando nele sem que se perca muito tempo tentando entender novamente o que ele faz;
- Inteligibilidade e `comentários`:
	Continuando o item anterior, escrever um programa legível é muito mais do que apenas escrever de uma forma esteticamente agradável, embora isso seja importante também. Existem muitas formas e metodologias para escrever programas, mas dentre todas as ferramentas possíveis para compreender um programa, o comentário é uma das mais importantes. Comentem seus programas. Em `Julia Language` um cometário é inciado com o caracter `#`, tal qual em python, e qualquer coisa escrita, naquela linha, após o `#` vai ser ignorado pelo programa. Comentários são pequenos textos, frases, ou até mesmo parágrafos que podem ser inseridos no meio do programa para que alguma anotação relevante (ou não) seja salva junto com o código. Veremos mais exemplos de comentários no futuro.;
- Pesquisa: 
	Dentre as mais importantes habilidades que um programador do século 21 pode ter é a capacidade de realizar buscas efetivas na internet. Essa habilidade é extremamente necessária, tendo em vista que a chance de você se deparar com um problema novo enquanto programa é quase certa. Copiar e colar programas da internet não é algo tão mal visto, desde que você procure entender e testar o código para ter certeza que ele realiza o que você precisa que ele realize. Assim como estudar física ou matemática exige você observar uma resolução pronta, copiar e matutar sobre ela por um tempo até entender. Tentar reproduzir uma conta, um programa, uma função ou uma tarefa já pronta é uma ótima forma de verificar se o seu processo de resolução de problemas está afiado o suficiente. Afinal, muitas vezes só existe uma resposta correta.
- Criatividade: 
	Considerando tudo que foi dito anteriormente, temos que nos lembrar que podem existir muitas formas diferentes de encontrar a resposta para um problema. Muitas vezes, utilizando a criatividade, podemos encontrar uma resposta muito mais simples para um problema do que se pensava anteriormente.


Para começarmos a escrever programas em `Julia Language` precisamos primeiramente instalar a linguagem. A discussão sobre conceitos da computação vai ser continuada na próxima sessão.


# Instalação da Linguagem Julia
A linguagem Julia é uma linguagem livre, gratuita, de código aberto com licença MIT. Podendo ser baixada e utilizada de forma gratuita. 
Site oficial da linguagem: https://julialang.org/. 
As instruções para download e instalação de cada plataforma estão disponíveis em https://julialang.org/downloads/platform/.
## PATH
O `PATH` ou `$PATH` é uma variável de ambiente de diferentes sistemas que nos diz o caminho dos arquivos executáveis disponíveis pelo sistema. Normalmente o diretório atual `.` já está incluído na variável `$PATH`, permitindo que possamos executar os programas localizados no diretório em que estamos no momento. 
Se quisermos executar um programa em Julia Language podemos executar o seguinte comando 
```bash 
/home/usuario/julia/bin/julia programa_exemplo.jl
```
ou se quisermos iniciar o `Julia REPL`, que será explicado em mais detalhes no capítulo [[Computação básica para física - 1 Introdução]], podemos executar o seguinte comando no terminal:
```bash 
/home/usuario/julia/bin/julia
```
Caso quisermos executar esse programa no terminal a partir de qualquer endereço sem ter que escrever todo o caminho necessário podemos adicionar a pasta `julia/bin` ao `PATH`, que consiste em simplesmente adicionar uma linha a um arquivo. 
### Bash terminal
Em sistemas com terminal bash isso pode ser feito adicionando a linha
```bash 
export PATH="$PATH:/home/usuario/julia/bin"
```
ao arquivo `.bashrc` (ou similar) que normalmente está no diretório do usuário, `/home/usuario/.bashrc`. Nesse caso o ponto no início do nome do arquivo significa que ele é um arquivo oculto, que não aparece normalmente no navegador de arquivos ou no terminal com o comando de listar arquivos. Para que possamos ver esses arquivos no terminal, por exemplo, precisamos adicionar a flag `-a` (_all = todos_) na parte final do comando:
```bash 
ls -a
```
### CMD do Windows
Para adicionar Julia Language ao `PATH` do Windows é necessário apenas assinalar a caixa `add Julia to PATH` durante o processo de instalação.
# O primeiro contato
Agora que o software da linguagem Julia está instalado no computador que vai utilizar, podemos começar escrever um programa simples diretamente no `Julia REPL`. Copie e cole a seguinte expressão no Julia REPL:
```julia
1 + 1
```
Em seguida tecle enter. 
Deverás ver o resultado: 
```julia
2
```
Também podemos somar todos os números de 0 a 10 utilizando executando o seguinte comando no REPL 
```julia
sum(0:10)
```
Podemos agora somar todos os números de 0 a 100 apenas trocando 10 por 100. 
```julia
sum(0:100)
```
Reitero que não é necessário entender tudo que está disposto nas _linhas de código_ que estão dispostas por enquanto, o objetivo desse material é te guiar enquanto você aprende a programar pela primeira vez, ou ainda é um programador iniciante. Expressões como essa:
```julia
begin 
	sqrt(6*sum([i for i in 0:1000]))
end
```
serão facilmente compreendidas em breve, logo mais, programas inteiros poderão ser compreendidos e escritos por você para pode criar programas que vão resolver as mais diversas tarefas que encontrar e que quiser automatizar ou resolver de forma mais simples. Realizar cálculos extensivos, encontrar valores aproximados para quantidades físicas em sistemas complexos ou não lineares, até mesmo encontrar respostas para problemas mais simples como os próprios sistemas lineares. Ou, quem sabe, escrever um programa que calcula $\pi$ até a segunda casa decimal utilizando o famoso resultado obtido por Leonard Euler, que a soma dos inversos dos quadrados dos números naturais é igual a $\pi^2$ dividido por 6, ou $$\sum_{n=1}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}.$$ No próximo capítulo teremos uma exposição dos conceitos introdutórios sobre desenvolvimento de software.

Os próximos exercícios são propositalmente simples e outros complexos, uma das principais habilidades de um programador do século 21 é aprender a pesquisar na internet as coisas que precisa aprender. Ser programador é estar em constante aprimoração das suas habilidades e conhecimentos. Quanto antes você superar a frustração constante de se deparar todo dia com o desconhecido, melhor. 
# Exercícios
## Fáceis
1. Utilize o Julia REPL para realizar alguns cálculos básicos de matemática. Com operações do tipo soma, subtração, divisão e multiplicação. Utilizando os símbolos $+$=`+`, $-$=`-`, $\div$=`/`  e $\times$=`*`.
2. Pelo terminal: Crie uma pasta dentro de outra pasta, escreva um arquivo na pasta e em seguida mostre onde esse arquivo se localiza. 
## Difíceis
1. Pesquise e aprenda a escrever um arquivo `.txt` simples utilizando o `vi` ou o `vim`.
