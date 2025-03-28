# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

X) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console. (CORRETA)

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.


______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

X) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.' CORRETA

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript ?????
//EX03 
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

X) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

X) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

X)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

X) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena. CORRETA

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

X) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

```javascript
//Resposta

let totalPedido = 200 //Variável que guarda o valor total do pedido

function frete(){ //Função que determina o frete de acordo com o total do pedido
    if (totalPedido < 50){ //Condição se o total do pedido for menor que 50
        console.log("Frete não disponível!");
    }
    else if (totalPedido >=50 || totalPedido <= 199){ //Condição se o total do pedido estiver entre 
        console.log("Frete com custo adicional!");
    }
    else { //Se não atender nehum dos requisitos acima, ou seja, maior que 200, o frete é gratis
        console.log("Frete grátis!"); 
    }
}

frete(); //Chama a função que mostra o resultado do frete depois de passar pelas condições
//Saída: Frete com custo adicional! 
´´´
______
```
**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação 5genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

```javascript
//Resposta:
class Veiculo { //Cria a classe Pai: veículo
    constructor(modelo, ano){ //Atributos que serão passados aos objetos da classe
        this.modelo = modelo; //Parâmetros do objeto
        this.ano = ano; //Parâmetros do objeto
    }

    caracteristicas(){ //método que mostra as características dos objetos que serão criados
        console.log(`Tipo do veículo: ${this.modelo}, Ano: ${this.ano}`); //Mostra as informações no console
    }

    calcularConsumo(distancia, eficiencia){ //Método usado para calcular o consumo do veículo
        let consumo = distancia/eficiencia; //Variável que guarda o cálculo do consumo (distância/eficiência)
        console.log(`Consumo: ${consumo} L.`); //Saída no console, mostrando o consumo
        return consumo; //retorna consumo
    }

}
class Carro extends Veiculo { //Classe carro, filha da classe Veículo
    constructor(modelo, ano, eficiencia){ //Atributos que serão passados aos objetos das classes
        super(modelo, ano) //Passa os parâmetros da classe pai (Veiculo) para a classe carro
        this.eficiencia = eficiencia //Parâmetro eficiência:distância (km) percorrida para cada litro de gasolina
    }

    caracteristicas(){ //Método características que foi herdado da classe pai
        console.log(`Tipo do carro: ${this.modelo}, Ano: ${this.ano}`);
    }

      calcularConsumo(distancia) { //Método calcular consumo herdado da classe pai
    return super.calcularConsumo(distancia, this.eficiencia); //Chama o método da classe pai (usando o super) e passa os argumentos (distancia e this.eficiencia)
}
}

let carro = new Carro("Ford", 2005, 10) //cria um novo objeto (carro) com a marca, ano e eficiência próprias
carro.caracteristicas(); //mostra as características na tala
carro.calcularConsumo(60); //calcula o consumo do carro, passando a distância = 60km

class Moto extends Veiculo { //Classe Moto, filha da classe Veículo
    constructor(modelo, ano, eficiencia){ //Atributos: modelos, ano e e ficiencia, são passados para a classe Moto
        super(modelo, ano) //Passa os parâmetros da classe pai (Veiculo) para a classe Moto
        this.eficiencia = eficiencia  //Parâmetro eficiência:distância (km) percorrida para cada litro de gasolina
      
    }

    caracteristicas(){  //Método características que foi herdado da classe pai
        console.log(`Tipo da moto: ${this.modelo}, Ano: ${this.ano}`);
    }

    calcularConsumo(distancia) { //Método calcular consumo herdado da classe pai
    return super.calcularConsumo(distancia, this.eficiencia); //Chama o método da classe pai (usando o super) e passa os argumentos (distancia e this.eficiencia)
}
}

let moto = new Moto("Bis", 2020, 30) //Cria novo objeto (moto), que recebe a marca, o ano e a eficiência
moto.caracteristicas(); //mostra as características da moto
moto.calcularConsumo(90); //calcula o consumo da moto em litros, ao percorrer 90km

/* Saída:
Tipo do carro: Ford, Ano: 2005
Consumo: 6 L.
Tipo da moto: Bis, Ano: 2020
Consumo: 3 L.
 */

´´´
______

```

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

```javascript
function tempoPouso(velocidadeInicial, velocidadeSegura, desaceleracao, tempoMaximo) { //função que calcula o tempo de pouso
    let tempo = 0; //tempo inicia em 0
    let velocidade = velocidadeInicial; //velocidade é passada como velocidadeInicial

    //enquanto a velocidade formaior que a velocidade segura, e o tempo for menor que o tempo máximo, a função ocorre
    while (velocidade > velocidadeSegura && tempo < tempoMaximo) { 
        velocidade -= desaceleracao; //desaceleração é subtraida da velocidade
        tempo++; //tempo é aumentado em 1s
    }

    if (velocidade <= velocidadeSegura) { //se a velocidade for menor ou igual que a velocidade segura, o pouso será realizado
        console.log(`Pouso bem sucedido em ${tempo} segundos.`);
    } else { // se não, o pouso falha
        console.log("Pouso não realizado, pois o tempo máximo foi atingido antes de alcançar a velocidade segura.");
    }
}
//testando a função, com os parâmetros
calcularTempoPouso(5000, 5, 50, 120);´

//Saída: Pouso bem sucedido em 100 segundos.
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos) 
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

```javascript

function multiplicarMatrizes(matrizA, matrizB) {
    // Verifica se as matrizes podem ser multiplicadas (colunas de A == linhas de B)
    if (matrizA[0].length !== matrizB.length) {
        return "As matrizes não podem ser multiplicadas, pois o número de linhas é diferente do de colunas.";
    }

    let linhasA = matrizA.length; //linhas da matriz A
    let colunasA = matrizA[0].length; //colunas da matriz a
    let colunasB = matrizB[0].length; //colunas da matriz B

    //criar a matriz resultado com dimensões (linhasA x colunasB)
    let matrizResultado = Array.from({ length: linhasA }, () => Array(colunasB).fill(0)); //cria um novo array a partir da multiplicação de linhasA por colunasB e preenche com 0

    //loop para multiplicação de matrizes
    for (let i = 0; i < linhasA; i++) { //passa pelas linhas de A
        for (let j = 0; j < colunasB; j++) { //passa pelas colunasB
            for (let k = 0; k < colunasA; k++) {//passa pelas colunasA
                matrizResultado[i][j] += matrizA[i][k] * matrizB[k][j]; //mostra a matriz resultado (linha*coluna)
            }
        }
    }

    return matrizResultado;//mostra a matriz resultado
}

//teste
let investimentos = [//matriz investimento
    [1000, 2000], 
    [1500, 2500]
];

let fatoresCrescimento = [//matriz fatores de crescimento
    [1.1, 0.9], 
    [1.2, 1.05]
];

let resultadoInvestimentos = multiplicarMatrizes(investimentos, fatoresCrescimento); //variável que guarda o resultado da multiplicação, feita através da função multiplicarMatrizes()

console.log("Resultado dos investimentos após crescimento:");
console.log(resultadoInvestimentos); //mostra o resultado da variável multiplicar matrizes

//Saída: 
Resultado dos investimentos após crescimento:
[ [ 3500, 3000 ], [ 4650, 3975 ] ]
```