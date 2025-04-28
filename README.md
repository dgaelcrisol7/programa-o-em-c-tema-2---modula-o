# programa-o-em-c-tema-2---modularizacao
programação em c  tema 2 - modularizacao
tema 2- introdução -  modularização

Itens iniciai - Preparação

Antes de iniciar o conteúdo deste tema, será necessário ter um compilador C instalado em sua máquina, como o GCC. Caso queira, instale o Dev-C++, que é um ambiente de desenvolvimento integrado livre que utiliza os compiladores do projeto GNU para compilar programas para o sistema operacional Microsoft Windows. Também será necessário possuir o arquivo com os códigos que serão utilizados neste tema. Clique aqui para fazer o download.


Objetivos

Descrever conceitos gerais de procedimentos e funções.
 
Identificar os tipos de funções predefinidas na linguagem C.
 
Distinguir passagem de parâmetros por valor e por referência.
 
Localizar o escopo das variáveis locais e globais.

Introdução

 demonstraremos como modularizar um programa na linguagem C usando funções e procedimentos, identificando os tipos de funções já predefinidas na biblioteca padrão do C. Relacionaremos, ainda, os tipos de passagem de parâmetros − por valor e por referência − identificando o escopo das variáveis como local e global.
----------
Considere um programa em linguagem C que precisa calcular a média de notas de alunos em diferentes disciplinas. Você decide aplicar a técnica de modularização. Quais são as vantagens de modularizar esse programa e como isso pode ser feito de maneira eficaz?

A modularização divide o programa em funções específicas, cada uma responsável por uma tarefa distinta, como entrada de dados, cálculo e exibição de resultados. Isso melhora a organização e a legibilidade do código, facilita a manutenção e permite a reutilização de funções em outros programas

------------------

tema 2 - modulo 1 -  Programação estruturada

Padronizando a forma de programar

A modularização é uma técnica fundamental na programação em C, que envolve a divisão do código-fonte em módulos autônomos e interconectados, facilitando a construção, a manutenção e a escalabilidade dos programas. Inspirada pela Revolução Industrial e a evolução da engenharia de software, a modularização permite a reutilização de código, a clareza na leitura e a eficiência no desenvolvimento. Vamos explorar a importância da modularização, suas vantagens, e como ela se integra com conceitos de programação estruturada, como funções e procedimentos, proporcionando aos alunos uma base sólida para a criação de software de alta qualidade.


Neste vídeo, vamos ver que a modularização em C divide o código-fonte em módulos autônomos, facilitando construção, manutenção e escalabilidade, permitindo a reutilização de código, clareza na leitura e eficiência no desenvolvimento.

História


Modularização é o ato ou efeito de modularizar ou tornar modular, isto é, o desenvolvimento, a construção ou a fabricação de algo em unidades ou peças autônomas que são passíveis de serem combinadas com outras para formarem um todo. No campo computacional, a modularização é empregada para dividir o programa em partes funcionais, partes essas que conversam umas com as outras.


Para entender melhor a definição de modularização, é necessário traçar um paralelo com a Revolução Industrial, que aconteceu na Inglaterra, no século XIX.

Sapateiro consertando um sapato.

Antes da Revolução Industrial, todo produto era manufaturado, ou seja, construído inteiro por um artesão e seu aprendiz. 

O sapateiro construía todo o sapato, desde a sola até o acabamento em couro, por exemplo. 

Para construir um conjunto de cadeiras, o marceneiro recebia a madeira e “esculpia” uma a uma.


Com o advento da Revolução Industrial, o trabalho passou a ser segregado. Uma pessoa construía uma parte da cadeira, − o assento, por exemplo − outra o encosto e outra montava. Tempos depois, a Ford chamou esse processo de linha de montagem, termo utilizado até hoje.


Dessa forma, um produto que era inteiriço passou a ser divido em módulos, que se interligavam e construíam o produto.


Na computação não foi muito diferente. O primeiro computador digital registrado, o ENIAC, não tinha o conceito de software, era tudo hardware. Porém, com a evolução da computação, em meados dos anos 1950, o cientista Von Neumann criou a arquitetura de computadores, cuja proposta inicial dividia o computador em três partes:

 

Entrada
 
Processamento
 
Saída

Começava, assim, a Revolução da Computação. As máquinas de Von Neumann, como são conhecidas as que adotam esse modelo, dividem o hardware do computador em três partes:

 

Unidade central de processamento
 
Dispositivos de entrada/saída
 
Memória

John Von Neumann introduziu o projeto lógico de computadores com programa armazenado na memória, modularizando o computador em partes como hardware e software.


Após essa fase, começaram a surgir os programas e o interesse comercial por computadores. Inicialmente, os programas eram escritos todos como um produto inteiriço, à semelhança de como era antes da Revolução Industrial. Sendo assim, algumas partes do código eram utilizadas mais de uma vez, o que deixava os programas com muita redundância no código, manutenção complicada e difícil, além da prática de utilizar os desvios com os “Go To”.


No final da década de 1960, então, ocorreu a crise do software, devido às dificuldades enfrentadas no seu desenvolvimento frente ao rápido crescimento da demanda, à complexidade dos problemas a serem resolvidos e à ausência de técnicas bem estabelecidas para o desenvolvimento de sistemas.


Foi nessa época, mais precisamente em 1968, que ocorreu a Conferência da OTAN sobre Engenharia de Software (NATO ‒ Software Engineering Conference) em Garmisch, Alemanha. O principal objetivo dessa reunião era estabelecer práticas mais maduras para o processo de desenvolvimento e, por essa razão, o encontro é considerado como o nascimento da disciplina de engenharia de software.


A criação da engenharia de software surgiu em uma tentativa de contornar a crise e dar um tratamento de engenharia (mais sistemático e controlado) ao desenvolvimento de sistemas de software complexos.


Ao lado da engenharia de software surgiu a programação estruturada, que possibilitou dividir o código em pedaços especializados e acoplá-los mais tarde, produzindo, assim, o software que atendia às necessidades comerciais com mais facilidade.


Vale destacar que o processo é semelhante à Revolução Industrial do século XIX, só que no final das décadas de 1960 e 1970.


Módulos


Como já visto anteriormente, a modularização consiste em decompor um programa em uma série de subprogramas individuais. Trata-se de um método utilizado para facilitar a construção de grandes programas, através de sua divisão em pequenas etapas.


A modularização segue o lema “dividir para conquistar”, ou seja, divide o problema em subproblemas menores, sucessivamente, conforme a necessidade.


A primeira etapa, por onde começa a execução do programa, é chamada de programa principal, e as demais são os subprogramas propriamente ditos, que são executados sempre que ocorre uma chamada, o que é feito através da especificação de seus nomes:


Programa principal

O programa principal é o ponto de entrada do software, onde a execução do código começa. Ele inicia as instruções e chama subprogramas ou funções auxiliares para cumprir a lógica e os objetivos do software.


Subprograma

É um programa que, geralmente, resolve um pequeno problema, e que está subordinado a um outro que solicitará seu acionamento. É possível que um subprograma chame outro subprograma.


Mas por que devemos modularizar?


A divisão do programa em módulos possui várias vantagens, entre elas:


Evitar que os programas fiquem grandes demais e difíceis de serem lidos e compreendidos.
 
Facilitar a leitura do código-fonte do programa.
 
Separar o programa em partes (blocos) que possam ser compreendidas de forma isolada (criação de módulos).
 
Evitar que um trecho seja repetido várias vezes dentro de um mesmo programa.
 
Permitir a alteração de um trecho do programa de forma mais rápida.
 
Utilizar um código em diferentes partes do programa, sem que ele precise ser escrito em cada local em que se deseje utilizá-lo.
 
Permitir o reaproveitamento de código já construído em outros programas (bibliotecas).

Ao dividir o programa em peças menores, será possível conectá-las para formar uma solução sempre que precisarmos resolver um problema mais complexo. Dessa forma, é necessário que essas peças sejam reutilizáveis, assim como blocos de montar.


Essas peças reutilizáveis podem ser chamadas de procedimentos e funções, que são formados por um bloco de código que executa uma determinada ação. De modo geral, cada função e cada procedimento deve realizar apenas uma ação, pois assim se tornam mais reutilizáveis e úteis para os programas.


Código estruturado


Inicialmente, os programas eram blocos lógicos, com início e fim, e compostos de estruturas de controle, como a de condição, seleção e repetição. Esses blocos consistiam em um conjunto de declarações e comandos delimitados pelas palavras início e fim, visando a aumentar a funcionalidade do programa.


Ao passo, porém, que os programas iam se tornando mais complexos, a divisão em partes menores os tornava mais claros e de fácil entendimento. Com o advento da programação estruturada, os programadores começaram a criar estruturas simples, usando as sub-rotinas.


Uma sub-rotina é uma ferramenta de programação que serve basicamente a dois objetivos:


1° Objetivo  - Evitar que uma sequência de comandos repetida em vários locais de um algoritmo tenha que ser escrita várias vezes.


2° Objetivo  - Dividir a estrutura de um algoritmo em partes fechadas e logicamente coerentes.


As sub-rotinas devem codificar a solução para um problema pequeno e específico. Elas podem ser funções ou procedimentos (quando não retornam valores):


Os procedimentos são estruturas que agrupam um conjunto de comandos, que são executados quando o procedimento é chamado.
 
As funções são um tipo especial de procedimento, no qual, depois de executada a chamada, o valor calculado é retornado no nome da função, que passa a ser uma variável da expressão. Ou seja, elas sempre retornam algum valor para quem chamou, diferentemente dos procedimentos, que não retornam valor algum.

Portanto, em um arquivo de programa, funções/procedimentos conversam com o programa principal, e vice-versa.

-------------

Funções e procedimentos


Funções são blocos de código que retornam um valor após sua execução, enquanto procedimentos, representados por funções do tipo void, executam ações sem retornar valores. Compreender esses conceitos é essencial para escrever programas modulares, eficientes e de fácil manutenção, permitindo a reutilização de código e melhor organização do projeto. A separação clara entre declaração e implementação de funções também será abordada, facilitando o desenvolvimento colaborativo e a leitura do código.

 mostrar a importância de compreender os conceitos de funções e procedimentos para programas modulares, eficientes e de fácil manutenção, permitindo a reutilização de código e melhor organização. Vai demonstrar, ainda, que a separação entre declaração e implementação facilita o desenvolvimento colaborativo e a leitura do código.

#include <stdio.h>

// Função para calcular o valor do desconto
float calcularDesconto(float preco, float percentual) {
    return preco * (percentual / 100);
}

// Procedimento para exibir o valor total com desconto
void exibirTotal(float preco, float desconto) {
    float total = preco - desconto;
    printf("O valor final com desconto: %.2f\n", total);
}

int main() {
    float preco, percentualDesconto, desconto;

    // Solicita o preço e o percentual de desconto do usuário
    printf("Digite o valor do produto: ");
    scanf("%f", &preco);

    printf("Digite o percentual de desconto: ");
    scanf("%f", &percentualDesconto);

    // Chama a função para calcular o desconto
    desconto = calcularDesconto(preco, percentualDesconto);

    // Chama o procedimento para exibir o total com desconto
    exibirTotal(preco, desconto);

    return 0;
}

Esse código em C serve para calcular o valor final de um produto após a aplicação de um desconto percentual. O usuário informa o preço original do produto e o percentual de desconto desejado. O programa então calcula o valor do desconto e subtrai do preço original. Em seguida, exibe o valor final com o desconto aplicado. É uma aplicação simples para treinar funções e entrada/saída de dados.

Explicação das funções e procedimentos do código:

#include <stdio.h>
Importa a biblioteca padrão de entrada e saída, necessária para usar printf() e scanf().

float calcularDesconto(float preco, float percentual)
É uma função que calcula o valor do desconto.
Ela recebe o preço do produto e o percentual de desconto, e retorna o valor descontado.

void exibirTotal(float preco, float desconto)
É um procedimento (função void, sem retorno) que calcula o valor final subtraindo o desconto do preço e exibe o resultado com printf().

int main()
É a função principal, onde o programa começa sua execução.
Nela, são declaradas variáveis, lidas as entradas do usuário, chamada a função de cálculo e o procedimento de exibição.

scanf() e printf()
São funções da biblioteca stdio.h. scanf() lê valores digitados pelo usuário e printf() exibe mensagens e resultados na tela.
--------------------

Funções


As funções são procedimentos que retornam um único valor ao final de sua execução.


No exemplo a seguir, apresentamos alguns casos, como as funções sqrt(), scanf() e printf(), que calculam a raiz quadrada, leem um número da entrada padrão e imprimem um valor na saída padrão. Veja

x = sqrt(4);
if (scanf ("%d", &x) == EOF)
printf("Fim de arquivo.\n");

-------------

Declarando uma função

Uma função em pseudolinguagem possui o seguinte formato:

funcao < nome-de-função >
2       [( < sequência-declarações-de-parâmetros >)]: < tipo-de-dado >
3       var
4       // Seção de Declarações Internas
5       inicio
6       // Seção de Comandos
7   fimfuncao		

-------------

Toda função deve ter um tipo que determina qual será o tipo de seu valor de retorno. Já os parâmetros de uma função determinam qual será o seu comportamento (como se fosse uma função matemática, na qual o parâmetro determina o valor da função). É possível, porém, que uma função não tenha parâmetros, basta não os informar. Na declaração a seguir, estão listados os parâmetros que serão utilizados na função:

tipo nome_da_funcao ( tipo < parametro1 >,
tipo < parametro2 >, . . . , tipo < parametron >) {
comandos;
return( valor de retorno );
}

---------------

É aconselhado declarar as funções antes do programa principal, mas o que ocorreria se declarássemos depois?


Embora aparentemente funcione, isso não pode ser feito na prática, pois alguns compiladores simplesmente não aceitam essa sintaxe, obrigando que a declaração ocorra antes da função main (ou melhor, antes de qualquer outra função que utilize uma determinada função).

A saída para a questão citada anteriormente seria fazer uma declaração da função antes da função main(), mas colocar a sua implementação depois dela. Declarar uma função sem a sua implementação é muito semelhante a declará-la com a implementação. Substituímos as chaves e seu conteúdo por ponto e vírgula, ou seja:


tipo nome_da_funcao ( tipo < parametro1 >,
tipo < parametro2 >, . . . , tipo < parametron >);

-----------

No exemplo a seguir, em linguagem C, somente declaramos a função imprime(), sem implementá-la:

void imprime (int numero);

Com isso, separamos a declaração da implementação, permitindo que ela possa vir em qualquer lugar do código (antes ou depois de qualquer outra função). Além disso, um programa que declara todas as funções antes de usá-las tende a ser mais claro, pois o programador já sabe qual o conjunto de funções que ele pode usar, sem se preocupar com a forma como elas foram implementadas (ou sequer como elas foram desenvolvidas, caso o código esteja sendo desenvolvido por uma equipe).

-------------

Exemplo de função - No exemplo a seguir, em linguagem C, identificamos a função soma() que realiza a soma de dois valores, que são passados por parâmetro:

												
1   int soma (int a, int b) {
2       return (a + b);
3   }

A expressão contida dentro do comando return é chamada de valor de retorno, e corresponde à resposta de uma determinada função. Esse comando é sempre o último a ser executado por uma função, e nada após ele será executado.


Quando utilizado, o comando return informa ao sistema operacional se o programa funcionou corretamente ou não. O padrão é que um programa retorne zero caso tenha funcionado corretamente, ou qualquer outro valor caso contrário.

-----------

Invocando uma função

Uma forma clássica de realizarmos a invocação (ou chamada) de uma função é atribuindo o seu valor a uma variável.

variavel = funcao (parametros);
-----

Na verdade, podemos invocar uma função em qualquer lugar onde faríamos a leitura de uma variável, mas nunca a escrita. Veja o exemplo a seguir.

-
printf ("Soma de x e y: %d\n", soma(x, y));
-

Nesse exemplo, ao executar a função printf será invocada a função soma, que irá calcular a soma das variáveis x e Y. Ao retornar a função, o resultado será apresentado na tela.


As variáveis passadas como parâmetros indicam os valores com os quais a função irá trabalhar. Esses valores são copiados para os parâmetros da função, que pode manipulá-los.


Os parâmetros passados pela função não necessariamente possuem os mesmos nomes que os que a função espera. Esses parâmetros serão mantidos intocados durante a execução da função.


O tipo void é um tipo especial, utilizado principalmente em funções. Ele representa o “nada”, ou seja, uma variável desse tipo armazena conteúdo indeterminado, e uma função desse tipo retorna um conteúdo indeterminado

----------------------------

Procedimentos


São estruturas que agrupam um conjunto de comandos, que são executados quando o procedimento é chamado, ou seja, procedimentos em linguagem C são funções do tipo void.


Declarando um procedimento

Um procedimento possui o seguinte formato:

1   procedimento < nome-de-procedimento >
2       [(< sequência-de-declarações-de-parâmetros >)]
3   var
4       // Seção de Declarações Internas
5   inicio
6       // Seção de Comandos
7   fimprocedimento	


Por exemplo, o procedimento a seguir imprime o número que for passado para ele como parâmetro:

1   void imprime (int numero) {
2       printf ("Número %d\n", numero);
3   }											


Ao se ignorar o valor de retorno de uma função e, para esta chamada, ela será equivalente a um procedimento.

-----------

Invocando um procedimento

Para invocarmos um procedimento, devemos utilizá-lo como utilizaríamos qualquer outro comando, ou seja:

procedimento (parametros);


-------------

Você está desenvolvendo um programa em C que deve calcular a soma de dois números e imprimir o resultado. Para isso, decide utilizar uma função para a soma e um procedimento para a impressão do resultado. Como você deve declarar e invocar essas funções e procedimentos de maneira adequada?

Para garantir que o compilador reconheça as assinaturas de funções e procedimentos, é recomendado declará-los antes da função main(). Isso permite que suas implementações possam ser localizadas em qualquer parte do código, facilitando a manutenção e a organização. A prática de declarar antes e implementar depois ajuda a manter um código mais limpo e legível, especialmente em projetos colaborativos. 


--------
tema 2 - mod 2. Bibliotecas padrão

--------

Você está desenvolvendo um programa em C que precisa ler duas strings do usuário, concatená-las e armazenar o resultado em uma terceira string. Quais funções você deve utilizar para realizar essas operações e qual seria a sintaxe correta para copiá-las e concatená-las?

A função strcpy é utilizada para copiar o conteúdo de uma string para outra, enquanto strcat é usada para concatenar duas strings. Portanto, a combinação dessas duas funções permite copiar as strings e depois concatená-las corretamente.

---------

tema 2 - mod 3 -  Usando funções 

Elementos sintáticos e semânticos das funções  - codigo videio (tempo) 14:20

- você vai ver os principais elementos sintáticos e semânticos da declaração de funções, destacando-se a passagem de parâmetros que pode ser feita por valor ou referência.

Passagem por valor


A primeira é através de uma cópia do valor do argumento na chamada da sub-rotina para o parâmetro declarado na sub-rotina, que se denomina passagem por valor.


Passagem por referência


A segunda maneira é através da passagem do endereço onde se encontra a variável usada como argumento na chamada da sub-rotina, conhecida por passagem por referência.

----
corrija o codigo e depois explique a passagem por valor e por referencia em no minimo 5 linhas cada. no final expliqque  em no minimo 10 linhas como o compilador le o codigo e inicializa a execução pela função principal main e depois realiza as outras tarefas: 



#include <stdio.h>

// Função que dobra o valor (passagem por valor)
void dobrar_valor(int num) {
    num = num * 2; // Apenas a cópia é modificada
    printf("Dentro da funcao (por valor), o valor dobrado é: %d\n", num);
}

// Função que dobra o valor (passagem por referência)
void dobrar_valor_ref(int *num) {  

*num = *num * 2;             // Modifica o valor original via ponteiro

    printf("Dentro da funcao (por referencia), o valor dobrado é: %d\n", *num);
}

int main() {
    int numero = 10;

    // Passagem por valor
    printf("Antes da funcao (por valor), o numero é: %d\n", numero);
    dobrar_valor(numero);
    printf("Depois da funcao (por valor), o numero é: %d\n", numero);

    // Passagem por referência
    printf("\nAntes da funcao (por referencia), o numero é: %d\n", numero);
    dobrar_valor_ref(&numero); // Passamos o endereço da variável
    printf("Depois da funcao (por referencia), o numero é: %d\n", numero);

    return 0;
}

💡 Explicação: Passagem por Valor (mínimo 5 linhas)
Na passagem por valor, uma cópia do valor da variável é passada para a função. Isso significa que qualquer alteração feita dentro da função não afeta a variável original. No exemplo acima, ao chamar dobrar_valor(numero), a função trabalha com uma cópia de numero. Mesmo que essa cópia seja modificada, o valor original permanece inalterado. Esse tipo de passagem é padrão em C para tipos primitivos como int, float, etc., pois é mais seguro, evitando efeitos colaterais indesejados.

🔁 Explicação: Passagem por Referência (mínimo 5 linhas)
Na passagem por referência, passamos o endereço da variável (usando ponteiros) para a função. Com isso, a função pode modificar diretamente o valor da variável original. No código, ao chamar dobrar_valor_ref(&numero), estamos dizendo para a função "aqui está o endereço onde o valor de numero está armazenado". A função então usa esse endereço para acessar e alterar o conteúdo real. Essa abordagem é útil quando se deseja que a função retorne várias alterações ou modifique diretamente dados sem precisar retornar valores.


🧠 Como o Compilador Lê e Executa o Código (mínimo 10 linhas)
Quando um código em C é compilado, o compilador (como o GCC) passa por diversas fases. Primeiramente, ele realiza uma análise léxica, convertendo o código-fonte em tokens (como palavras-chave, identificadores e operadores). Em seguida, faz uma análise sintática, verificando a estrutura gramatical do código, e depois uma análise semântica, onde verifica tipos de variáveis, chamadas válidas de funções, e outros detalhes lógicos.

Após isso, o compilador converte o código em código de máquina (binário), adequado ao processador. Quando esse programa binário é executado, a função main() é sempre o ponto de entrada, ou seja, é a primeira função que o sistema operacional chama para iniciar o programa.

Dentro de main(), o fluxo de execução segue de cima para baixo. Ele executa os printf para exibir o valor da variável, chama dobrar_valor (que roda e retorna), e depois imprime novamente o valor. O mesmo acontece para dobrar_valor_ref, com a diferença de que ela altera o valor original.

Durante toda a execução, a memória é dividida em áreas como:

Stack (pilha) – onde ficam variáveis locais e chamadas de funções.

Heap (alocação dinâmica) – para dados que são criados dinamicamente.

Code segment – onde está o código compilado.

Data segment – onde ficam variáveis globais.

-------------
tema 2 - mod 3 - 
codigo exemplo 8  material estacio

Para passar um vetor para uma função usando linguagem C, utiliza-se um ponteiro como parâmetro da função. Ao usarmos o ponteiro como parâmetro, estamos passando o endereço inicial do vetor, não os seus elementos. Veja:

#include <stdio.h>

void v_iniciacao(int *vet, int n) {
    int i;
    for (i = 0; i < n; i++)
        vet[i] = 0;
}

void v_imprime(int *vet, int n) {
    int i;
    for (i = 0; i < n; i++)
        printf("%d - ", vet[i]); 
    printf("\n");
}

int main(void) {
    int vet[10], i;

    v_iniciacao(vet, 10);

    // Impressão após inicialização
    printf("Impressão do vetor antes da atribuição:\n");
    v_imprime(vet, 10);

    // Atribuindo valores ao vetor
    for (i = 0; i < 10; i++) {
        vet[i] = i;
    }

    // Impressão após atribuição
    printf("Impressão do vetor após a atribuição:\n");
    v_imprime(vet, 10);

    return 0;
} 

resultado

Impress├úo do vetor antes da atribui├º├úo:
0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 -
Impress├úo do vetor ap├│s a atribui├º├úo:
0 - 1 - 2 - 3 - 4 - 5 - 6 - 7 - 8 - 9 -

--------------------------------
Process exited after 31.57 seconds with return value 0
Pressione qualquer tecla para continuar. . .

---------------
tema 2 - mod 3 - 

Passagem de vetores
A passagem de vetores para funções em C é sempre realizada por referência, permitindo que as funções modifiquem diretamente os elementos do vetor original. A sintaxe para passar um vetor a uma função utiliza um ponteiro, indicando o endereço inicial do vetor. Isso possibilita a manipulação eficiente de grandes conjuntos de dados sem a necessidade de copiar todos os elementos. Vamos explorar como declarar, inicializar e manipular vetores dentro de funções, destacando a importância de entender a passagem de vetores por referência para criar programas eficientes e bem estruturados.


Neste vídeo, vamos ver a passagem de um vetor como parâmetro de uma função. A passagem de vetores é peculiar, e vamos ver o motivo.

Passagem de vetores codigo do video (tempo) 16:30 

A passagem de vetores para funções em C é sempre realizada por referência, permitindo que as funções modifiquem diretamente os elementos do vetor original. A sintaxe para passar um vetor a uma função utiliza um ponteiro, indicando o endereço inicial do vetor. Isso possibilita a manipulação eficiente de grandes conjuntos de dados sem a necessidade de copiar todos os elementos.

#include <stdio.h>

// Função que calcula a soma dos elementos de um vetor
int calcular_soma(int *vetor, int tamanho) {
    int soma = 0;
    int i;
    for (i = 0; i < tamanho; i++) {
        soma += vetor[i]; // Soma cada elemento
    }
    return soma;
}

int main() {
    // Definindo um vetor de inteiros
    int lista_compras[] = {10, 20, 30, 40, 50};
    
    // Calculando o tamanho do vetor
    int tamanho = sizeof(lista_compras) / sizeof(lista_compras[0]);

    // Chamando a função para calcular a soma do vetor
    int total = calcular_soma(lista_compras, tamanho);

    // Exibindo o resultado
    printf("O total da lista de compras: %d\n", total);

    return 0;
}

---
O que a função void retorna?
A palavra-chave void em C significa literalmente “vazio”. Quando dizemos que uma função é void, como em void v_iniciacao(...), estamos dizendo que essa função não retorna nenhum valor.
Ou seja, ela executa uma tarefa, mas não entrega um resultado para ser usado depois.
-----


A passagem de vetores para funções é sempre por referência. A sintaxe de passagem de um vetor pode ser feita com:

tipo nome[ ];


Onde: Tipo corresponde ao tipo dos elementos do vetor, nome é o nome atribuído ao vetor e [ ] indica que a variável é do tipo vetor.


O “[ ]” pode ser utilizado sem um valor, pois em C não interessa qual a dimensão do vetor que é passado a uma função, mas, sim, o tipo dos seus elementos.
----
📌 Como o vetor foi utilizado por referência (explicação em 7 linhas)
Quando um vetor é passado para uma função em C, ele não é copiado como uma variável comum. Em vez disso, o endereço do primeiro elemento do vetor é enviado à função, ou seja, ele é passado por referência. Isso permite que a função acesse os mesmos dados armazenados na memória do vetor original. No código acima, usamos a sintaxe int *vetor na função calcular_soma, que significa que vetor é um ponteiro para um inteiro — ou seja, ele aponta para o início do array. Assim, vetor[i] acessa os elementos diretamente da memória original, sem duplicação de dados. Isso torna a execução mais eficiente e permite alterar os valores originais, se necessário.

📌 Sintaxe: passando vetor como ponteiro

// Declaração da função com ponteiro:
int calcular_soma(int *vetor, int tamanho);

// Chamada da função no main:
int total = calcular_soma(lista_compras, tamanho);
Essa sintaxe é equivalente a:


int calcular_soma(int vetor[], int tamanho);
Internamente, ambas são interpretadas como ponteiro para o primeiro elemento do vetor.

---

Para entender melhor a definição, observe o Programa 8. Ele declara uma função v_iniciacao(), que inicializa o vetor de inteiros com zero. Em seguida, o vetor de 10 posições é alimentado por números inteiros de 0 a 9 e, por último, a função v_imprime() imprime os valores do vetor.


Para passar um vetor para uma função usando linguagem C, utiliza-se um ponteiro como parâmetro da função. Ao usarmos o ponteiro como parâmetro, estamos passando o endereço inicial do vetor, não os seus elementos. Veja:

#include <stdio.h> // Removido o espaço incorreto

// Função que inicializa o vetor com zeros
void v_iniciacao(int *vet, int n) {
    int i;
    for (i = 0; i < n; i++) {
        vet[i] = 0;
    }
}

// Função que imprime os valores do vetor
void v_imprime(int *vet, int n) {
    int i; // Corrigido: estava declarado como "I"
    for (i = 0; i < n; i++) {
        printf("%d - ", vet[i]);
    }
    printf("\n");
}

// Função principal
int main(void) {
    int vet[10];
    int i;

    // Inicializa o vetor com zeros
    v_iniciacao(vet, 10);

    // Impressão após inicialização
    printf("Impressao do vetor antes da atribuicao:\n");
    v_imprime(vet, 10);

    // Atribui valores ao vetor
    for (i = 0; i < 10; i++) {
        vet[i] = i;
    }

    // Impressão após atribuição
    printf("Impressao do vetor apos a atribuicao:\n");
    v_imprime(vet, 10);

    return 0;
}

resposta no console 

Impressao do vetor antes da atribuicao:
0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 -
Impressao do vetor apos a atribuicao:
0 - 1 - 2 - 3 - 4 - 5 - 6 - 7 - 8 - 9 -

--------------------------------
tema 2 mod 3 - Usando funções

Usando passagem de parâmetros na prática

Na linguagem C, a passagem de parâmetros em sub-rotinas, como funções e procedimentos, é um conceito fundamental que afeta diretamente a forma como os dados são manipulados e compartilhados dentro de um programa. Existem duas principais formas de passagem de parâmetros: por valor e por referência. 

 

Na passagem por valor, uma cópia do valor do argumento é passada para a sub-rotina, o que significa que alterações feitas no parâmetro dentro da sub-rotina não afetam a variável original. Por outro lado, na passagem por referência, o endereço da variável é passado para a sub-rotina, permitindo que alterações feitas no parâmetro afetem diretamente a variável original. 

 

Essa técnica é especialmente útil para manipular grandes estruturas de dados, como vetores e estruturas complexas, sem a sobrecarga de copiar os dados inteiros. Entender quando e como usar cada tipo de passagem de parâmetro é essencial para escrever programas eficientes e bem-organizados em C.


Neste vídeo, vamos acompanhar a elaboração de uma função e usar os mecanismos de passagem de parâmetros.

---

Passo 1: Definição da função dobrar_valor utilizada na passagem de parâmetro por valor.
Passo 2: Definição da função dobrar_valor_ref utilizada na passagem de parâmetro por referência.
Passo 3: Implementação do programa principal



#include <stdio.h>

// Função que dobra o valor (passagem por valor)
void dobrar_valor(int num) {
    num = num * 2;  // Modifica apenas a cópia do valor
    printf("Dentro da função (por valor), o valor dobrado é: %d\n", num);
}

// Função que dobra o valor (passagem por referência)
void dobrar_valor_ref(int *num) {
    *num = *num * 2;  // Modifica o valor original usando o ponteiro
    printf("Dentro da função (por referência), o valor dobrado é: %d\n", *num);
}

int main() {
    int numero = 10;

    // Passagem por valor
    printf("Antes da função (por valor), o número é: %d\n", numero);
    dobrar_valor(numero); // Chama função que recebe uma cópia
    printf("Depois da função (por valor), o número é: %d\n", numero);

    // Passagem por referência
    printf("\nAntes da função (por referência), o número é: %d\n", numero);
    dobrar_valor_ref(&numero); // Passa o endereço da variável
    printf("Depois da função (por referência), o número é: %d\n", numero);

    return 0;
}
    
saida no console

Antes da fun├º├úo (por valor), o n├║mero ├®: 10
Dentro da fun├º├úo (por valor), o valor dobrado ├®: 20
Depois da fun├º├úo (por valor), o n├║mero ├®: 10

Antes da fun├º├úo (por refer├¬ncia), o n├║mero ├®: 10
Dentro da fun├º├úo (por refer├¬ncia), o valor dobrado ├®: 20
Depois da fun├º├úo (por refer├¬ncia), o n├║mero ├®: 20

--------------------------------
Você está desenvolvendo um programa em C que deve calcular a média de um conjunto de notas armazenadas em um vetor. A função que calcula a média deve receber o vetor de notas e o número de elementos no vetor. Como você deve declarar e implementar essa função, e como deve chamar a função no programa principal?

resposta 

Para calcular a média dos elementos de um vetor, a função deve ser capaz de acessar todos os elementos do vetor. Declarar a função utilizando ponteiros permite passar o vetor por referência, evitando a cópia desnecessária de dados e permitindo a manipulação direta dos elementos do vetor.

----------------------------

tema 2 mod 4 - Regras de escopo em C

O que é escopo - Em linguagens de programação, o escopo das variáveis define onde e como essas variáveis podem ser acessadas. Na linguagem C, as variáveis podem ser classificadas em três tipos de escopo: variáveis locais, variáveis globais e parâmetros formais. Variáveis globais são declaradas fora de sub-rotinas e podem ser acessadas por qualquer parte do programa. Variáveis locais são declaradas dentro de sub-rotinas e só podem ser usadas dentro dessas sub-rotinas. Parâmetros formais são declarados na lista de parâmetros de uma sub-rotina e são utilizados exclusivamente dentro da sub-rotina onde são definidos. Compreender esses conceitos é fundamental para gerenciar dados e funções de forma eficiente em um programa.


Você vai ver que o escopo das variáveis em C define onde e como elas podem ser acessadas. Verá ainda que variáveis podem ser locais, globais ou parâmetros formais, determinando sua disponibilidade e uso dentro do programa. 

Nas linguagens de programação, as variáveis são vinculadas aos seus valores em tempo de execução. E o escopo de uma vinculação é o conjunto de trechos de um programa que se consegue usar as variáveis.


No caso da linguagem c, as variáveis são divididas quanto ao escopo em três tipos:
 

Variáveis locais
 
Variáveis globais
 
Parâmetros formais

Sendo assim, podemos declarar as variáveis em três locais distintos:


Primeiro local

Fica fora das sub-rotinas de um programa. Essas são chamadas de variáveis globais e podem ser usadas a partir de qualquer lugar do programa. Como elas estão fora das sub-rotinas, podemos dizer que todas as funções as veem.

Segundo local

Fica dentro da sub-rotina de um programa. Essas são chamadas de variáveis locais e só têm validade dentro da sub-rotina no qual são declaradas, isto é, só a sub-rotina em que a variável é declarada sabe da sua existência.

Terceiro local

Está na lista de parâmetros de uma sub-rotina. Essas são chamadas de parâmetros formais e são declaradas na definição dos parâmetros de uma sub-rotina. Apesar de receberem valores externos, elas são conhecidas apenas pela sub-rotina onde são declaradas.

---------------
Você está desenvolvendo um programa em C que calcula a soma de dois números e imprime o resultado. Para isso, você utiliza uma função soma que recebe dois parâmetros. Como você deve declarar as variáveis que armazenam os números e o resultado para que sejam acessíveis em toda a função main e na função soma?

Declarar as variáveis dentro da função main e passar os valores como parâmetros para a função soma é a prática mais adequada, pois mantém o escopo das variáveis limitado ao contexto em que são necessárias, evitando efeitos colaterais indesejados e tornando o código mais modular e fácil de entender. A opção Essa  é a correta porque promove boas práticas de programação, enquanto as outras opções utilizam escopos inadequados ou ineficientes para essa situação.

------------------

TEMA 2 - MOD 4 - Regras de escopo em C

Variáveis locais e globais - O escopo das variáveis em C define onde e como as variáveis podem ser acessadas dentro de um programa. As variáveis podem ser classificadas como locais, globais ou parâmetros formais. Variáveis locais são declaradas dentro de sub-rotinas e só são acessíveis dentro dessas sub-rotinas. Variáveis globais são declaradas fora de qualquer sub-rotina e podem ser acessadas por todo o programa. Parâmetros formais são variáveis locais que são declaradas na lista de parâmetros de uma sub-rotina e recebem valores quando a sub-rotina é chamada. Compreender o escopo das variáveis é crucial para escrever programas claros e evitar conflitos de nomes e erros.


Este vídeo vai demonstrar que o escopo das variáveis em C determina onde e como elas podem ser acessadas. Mostra também que podem ser locais, globais ou parâmetros formais, impactando a visibilidade e uso dentro do programa.





Variáveis locais


As variáveis locais são declaradas dentro de um bloco de código de uma sub-rotina. Só podem ser usadas ou modificadas pela sub-rotina onde estão declaradas, isto é, dentro desta ou do bloco de código do programa.


Curiosidade
A existência dessas variáveis depende da execução da sub-rotina onde estão declaradas, isso significa que somente existem enquanto a sub-rotina onde foi declarada estiver sendo executada.

Conforme visualizado no Programa  A seguir , a seguir, na linha 5 foram declaradas na função principal main()três variáveis locais: num1, num2 e num3, isto é, essas três variáveis pertencem à função principal main() e seu escopo está relacionado à execução da função.

#include <stdio.h>  // Correção: removidos os espaços indevidos

int main() {
    int num1, num2, num3;

    num1 = 10;
    num2 = 20;
    num3 = num1 + num2;

    printf("%d + %d = %d\n", num1, num2, num3);

    return 0;
}	

respota console  = 10 + 20 = 30

Qualquer valor que as variáveis num1, num2 e num3 assumam será válido apenas dentro da função main. Supondo que existisse uma sub-rotina nesse programa, essas variáveis não poderiam ser acessadas.

--------------------------------

Variáveis globais


As variáveis globais são declaradas fora da sub-rotina. São acessíveis em todos os escopos, em qualquer ponto de um programa, mesmo em outros módulos.


Podem, portanto, ser usadas ou modificadas por qualquer sub-rotina do programa onde estão declaradas. Em outras palavras, as variáveis globais estão disponíveis durante toda a execução do programa.


O valor de uma variável global ao longo do ciclo de vida do programa é sempre válido. Conforme visualizado no Programa 10, na linha 3 foi declarada a variável num3 como uma variável global:

#include <stdio.h>  // Correção: removidos os espaços extras

int num3;  // Variável global

int main() {
    int num1, num2;

    num1 = 10;
    num2 = 20;
    num3 = num1 + num2;

    printf("%d + %d = %d\n", num1, num2, num3);

    return 0;
}

respota console = 10 + 20 = 30
--------------
Em um programa, as variáveis locais e as globais podem ter o mesmo identificador, isto é, o mesmo nome. Porém, dentro de uma sub-rotina, as variáveis locais sobrepõem o valor das globais.


No Programa a sequir , apresentado a seguir, encontramos uma declaração de variável global e variável local com o mesmo nome nas linhas 3 e 7, respectivamente, que é a variável num

Comentário
Repare que na linha 4 a variável global num recebe o valor 20. Esse valor é válido apenas externamente à função main. Como nesta existe uma variável com o mesmo nome, quando, na linha 8, a variável num recebe o valor 10, esta é a mais interna ao programa, ou seja, a variável local que foi definida na linha 7.

Para comprovar, vamos executar o Programa a sequir . Podemos observar que, ao executar a função printf na linha 9, o valor impresso será o valor 10, que é o atribuído a variável local num:

// Programa  - imprime o valor da variável num

#include <stdio.h>     // Corrigido: removidos os espaços extras
 int num;
 num = 20;          // Declaração e inicialização correta da variável global

int main() {
    int num;           // Variável local com o mesmo nome da global
    num = 10;          // Atribuição à variável local

    printf("O valor da variavel num: %d\n", num);  // Imprime a variável local

    return 0;
}

respota console = O valor da variavel num: 10

--------------------------------
Parâmetros formais

Os parâmetros formais de uma sub-rotina também são variáveis locais. Eles são declarados como sendo as entradas de uma sub-rotina, sendo assim, são variáveis locais da função. É possível alterar o valor de um parâmetro formal, pois essa alteração não terá efeito na variável que foi passada à sub-rotina.


Na linguagem C, quando se passa parâmetros para uma sub-rotina, são passadas apenas cópias das variáveis. Isso significa que os parâmetros formais existem independentemente das variáveis que foram passadas para a sub-rotina, eles tomam apenas uma cópia dos valores passados.


Comentário
Observando o Programa 12, a seguir, na linha 7 foi declarada a função soma com dois parâmetros formais, x e y. Essa função recebe dois números inteiros e retorna a soma desses dois números.

Na linha 18, a variável local num3 recebe o retorno da função soma.


Os parâmetros formais da função soma() são variáveis locais dessa função, seus valores são visíveis somente durante a execução da função.


// Programa 12: soma dois números
#include <stdio.h>  // Corrigido: removidos os espaços extras

// Variável global
int num3;

// Função soma
int soma(int x, int y) {
    int v_soma;
    v_soma = x + y;
    return v_soma;
}

int main() {
    int num1, num2;

    num1 = 10;
    num2 = 20;

    num3 = soma(num1, num2);

    printf("%d + %d = %d\n", num1, num2, num3);

    return 0;
}


respota console = 10 + 20 = 30


Nesse exemplo, podemos observar ainda sobre variáveis globais: Repare que na linha 4 foi definida a variável global num3. Agora considere que também tenha sido declarada uma variável global num1. Como visto anteriormente, como também há a num1 na função main, a que será manipulada dentro da função main é a variável local declarada na linha 15, portanto, assumindo o valor 10.


E o que aconteceria se na função soma fosse utilizada a variável num1? Qual das duas variáveis num1 seria acessada? Claro que seria a variável global num1, que tem escopo em qualquer parte do programa.


--------------------------------

Você está desenvolvendo um programa em C que deve calcular a soma de dois números e armazenar o resultado em uma variável global. Para isso, você utiliza uma função soma que recebe dois parâmetros. Onde você deve declarar a variável que armazenará o resultado da soma para que ela seja acessível tanto no programa principal quanto na função soma?

resposta ?

Para que a variável que armazena o resultado da soma seja acessível tanto no programa principal quanto na função soma, ela deve ser declarada como global. Declarar a variável fora de qualquer sub-rotina garante que ela possa ser acessada e modificada por qualquer parte do programa. As outras opções são inadequadas porque declaram a variável em um escopo que não permite seu acesso em ambas as funções ou utilizam técnicas não necessárias para esse cenário específico.
----------------------------------
tema 2 - mod 4 -  Regras de escopo em C

Usando escopo na prática

O escopo das variáveis na linguagem C define onde e como as variáveis podem ser acessadas dentro de um programa. Existem três tipos principais de escopo: variáveis locais, variáveis globais e parâmetros formais. Variáveis locais são declaradas dentro de sub-rotinas e só podem ser usadas dentro dessas sub-rotinas, existindo apenas durante a execução delas. Variáveis globais são declaradas fora de qualquer sub-rotina e podem ser acessadas por qualquer parte do programa, mantendo seu valor ao longo de toda a execução do programa. 

 

Parâmetros formais são variáveis locais que são declaradas na lista de parâmetros de uma sub-rotina e são usadas para receber valores quando a sub-rotina é chamada. A compreensão do escopo das variáveis é essencial para evitar conflitos de nomes e garantir que os dados sejam manipulados corretamente em diferentes partes do programa. O uso adequado do escopo das variáveis ajuda a criar programas mais organizados, eficientes e fáceis de manter.


Nesta atividade, vamos explorar as regras de escopo da linguagem C e observar o comportamento e as consequências dessas regras.

codigo do video  

- Usando escopo na prática - tempo - 11: 45 

 explique as funçoes do codigo em  no minimo 10 linhas: #include <stdio.h> 

// Variável global para o total de itens no estoque
int totalEstoque = 100;

// Função para adicionar itens ao estoque
void adicionarEstoque(int quantidade) {
    totalEstoque += quantidade;
    printf("Itens adicionados: %d\n", quantidade);
    printf("Estoque atualizado: %d\n", totalEstoque);
}

// Função para remover itens do estoque
void removerEstoque(int quantidade) {
    if (quantidade <= totalEstoque) {
        totalEstoque -= quantidade;
        printf("Itens removidos: %d\n", quantidade);
        printf("Estoque atualizado: %d\n", totalEstoque);
    } else {
        printf("Erro: Quantidade insuficiente no estoque!\n");
    }
}

// Função principal
int main() {
    int quantidade;

    // Adicionar itens ao estoque
    quantidade = 28;
    adicionarEstoque(quantidade);

    // Remover itens do estoque
    quantidade = 15;
    removerEstoque(quantidade);

    // Tentar remover uma quantidade maior do que o estoque
    quantidade = 200;
    removerEstoque(quantidade);

    return 0;
}

resposta console: Itens adicionados: 28
Estoque atualizado: 128
Itens removidos: 15
Estoque atualizado: 113
Erro: Quantidade insuficiente no estoque!

--------------------------------
Process exited after 30.39 seconds with return value 0
Pressione qualquer tecla para continuar. . .


Este código em C implementa um controle simples de estoque utilizando funções para adicionar e remover itens. A variável global totalEstoque é usada para armazenar a quantidade total de itens disponíveis e é inicializada com o valor 100.

A função adicionarEstoque(int quantidade) serve para aumentar o número de itens no estoque. Ela recebe como argumento a quantidade a ser adicionada, soma esse valor à variável global totalEstoque e imprime na tela quantos itens foram adicionados, além do novo total.

A função removerEstoque(int quantidade) tem o objetivo de remover itens do estoque, mas só permite isso se a quantidade solicitada for menor ou igual ao valor atual do estoque. Se houver estoque suficiente, a função subtrai a quantidade informada e exibe uma mensagem com o novo total. Caso contrário, imprime uma mensagem de erro informando que não há itens suficientes.

A função main() é o ponto de partida do programa. Dentro dela, a variável local quantidade é usada para armazenar valores que serão passados para as funções de adicionar e remover. Primeiro, são adicionados 28 itens. Depois, são removidos 15. Por fim, o código tenta remover 200 itens, o que gera um erro, pois o estoque não tem essa quantidade disponível.

O código serve como um exemplo prático de como usar funções para modularizar tarefas, trabalhar com variáveis globais, e aplicar condições para controle de fluxo no programa. É uma boa base para sistemas simples de gerenciamento.


----------------------


Roteiro de prática

Passo 1: Definição da variável global

#include <stdio.h> 

// Variável global para o total de itens no estoque 

int totalEstoque = 100;

Passo 2:

Definição da função adicionarEstoque utilizada na adição de itens ao estoque.

// Procedimento para adicionar itens ao estoque 

void adicionarEstoque(int quantidade) {  // 'quantidade' é um parâmetro formal 

    totalEstoque += quantidade; 

    printf("Itens adicionados: %d\n", quantidade); 

    printf("Estoque atualizado: %d\n", totalEstoque); 

}

Passo 3:

Definição da função removerEstoque utilizada na remoção de itens do estoque.

// Procedimento para remover itens do estoque 

void removerEstoque(int quantidade) {  // 'quantidade' é um parâmetro formal 

    if (quantidade <= totalEstoque) { 

        totalEstoque -= quantidade; 

        printf("Itens removidos: %d\n", quantidade); 

        printf("Estoque atualizado: %d\n", totalEstoque); 

    } else { 

        printf("Erro: Quantidade insuficiente no estoque!\n"); 

    } 

Passo 4: Implementação do programa principal

// Função principal 

int main() { 

    // Variável local para armazenar a quantidade de itens a ser processada 

    int quantidade; 

 

    // Adicionar itens ao estoque 

    quantidade = 20;  // 'quantidade' é um argumento passado para a função 

    adicionarEstoque(quantidade); 

 

    // Remover itens do estoque 

    quantidade = 15;  // 'quantidade' é um argumento passado para a função 

    removerEstoque(quantidade); 

 

    // Tentar remover uma quantidade maior do que o estoque 

    quantidade = 200;  // 'quantidade' é um argumento passado para a função 

    removerEstoque(quantidade); 

 

    return 0; 

}	

Passo 7: Exploração adicional

-Modifique o programa para adicionar novas variáveis locais e globais.
 -Experimente declarar uma variável global para armazenar o resultado e modifique a função soma para usar essa variável global.
 -Observe as mudanças no comportamento do programa e discuta as implicações do uso de variáveis globais versus locais.
Exemplo de modificação adicional
Adicionando uma variável global

 Declare uma variável global fora de qualquer sub-rotina.

#include <stdio.h>

int soma(int x, int y); // Protótipo da função
int resultado_global; // Variável global

int main() {
    int num1, num2;
    
    // Inicializa as variáveis
    num1 = 10;
    num2 = 20;
    
    // Chama a função soma e armazena o resultado na variável global
    resultado_global = soma(num1, num2);
    
    // Imprime o resultado
    printf("%d + %d = %d\n", num1, num2, resultado_global);
    
    return 0;
}
int soma(int x, int y) {
    return x + y;
}
resposta console 

  10 + 20 = 30
--------------------------------

Compile e execute novamente o programa para observar o comportamento com a variável global.

-----------------

Você está desenvolvendo um programa em C que deve calcular a soma de dois números, armazenar o resultado em uma variável e imprimir o resultado. A função soma deve receber dois parâmetros. Onde você deve declarar a variável que armazenará o resultado para garantir que ela seja acessível no programa principal e na função soma?


Declarar a variável que armazenará o resultado da soma como local dentro da função main e retornar o resultado da função soma é a prática mais adequada. Isso mantém o escopo das variáveis limitado ao contexto no qual são necessárias, evitando efeitos colaterais indesejados e tornando o código mais modular e fácil de entender. A opção B é correta porque promove boas práticas de programação

---------------------------

Considerações finais

-Conceito de escopo de variáveis em C.
 -Diferença entre variáveis locais, variáveis globais e parâmetros formais.
 
-Utilização de variáveis locais dentro de sub-rotinas.
 
-Acesso e modificação de variáveis globais em todo o programa.
 
-Importância dos parâmetros formais como variáveis locais.
 
-Passagem de parâmetros por valor e por referência.
 
-Declaração e uso de protótipos de funções.
 
-Manipulação de vetores através de passagem por referência.
 
-Implementação prática de funções para cálculo e manipulação de dados.
 
Práticas recomendadas para organização e modularidade do código em C.


----------------------------


