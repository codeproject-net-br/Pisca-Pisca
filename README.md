# Projeto 1 - Pisca-Pisca

Neste primeiro projeto iremos fazer uma luz piscar. Parece um projeto simples demais, mas isso exemplifica a utilização do Arduino para controle de dispositivos externos. Os conceitos aprendidos neste exemplo servem para acionamento de outros dispositivos como ventilador, lâmpadas, motores e etc.

<img src="https://uploads.filipeflop.com/2018/12/PROJETO001.gif" width="100%">

Fazer uma luz piscar é um projeto tão importante, que existe até uma competição internacional para ver quem faz uma luz piscar de maneira mais impressionante, mostrando domínio de eletrônica e programação. É o primeiro passo que se dá quando se começa a trabalhar com uma placa, porque ele mostra que você é capaz de programá-la. Esse primeiro projeto será um pequeno grande passo para que você aprenda eletrônica e programação e possa fazer projetos mais complexos.

Sabemos que o guia para este primeiro projeto está bastante longo, mas depois que você entende como funciona, não irá precisar de tantas instruções para conseguir reproduzir um projeto.

## Material necessário

Em todos os projetos teremos uma seção que mostra os componentes que iremos utilizar. Se você tiver alguma dúvida sobre qual é o componente, você pode voltar na lista de materiais:

* 1x LED Vermelho 5 mm
* 1x Resistor 220 ohm
* 1x Protoboard
* 2x Jumper macho-macho
* 1x Cabo USB
* 1x Placa Uno

## Montagem do projeto

No caso do nosso projeto, a fonte de energia vem da porta 11 do Arduino. Com a programação correta, é possível ligar e desligar a energia do pino 11, fazendo o LED acender e apagar.

No esquema da montagem do circuito, as linhas coloridas são a representação gráfica dos jumpers. Utilize-os para ligar os componentes entre si conforme a ilustração abaixo. Note que o pino 11 está conectado ao lado positivo do LED, enquanto o GND vai no pino negativo, passando antes pelo resistor.

<img src="https://uploads.filipeflop.com/2018/12/projeto_01_bb-1024x555.png" width="100%">

A representação de um circuito da montagem acima seria a seguinte:

<img src="https://uploads.filipeflop.com/2018/12/circuito-projeto1.png" width="100%">

Não é necessário conectar os componentes exatamente nos mesmos furos como indicados acima, basta apenas que os terminais de cada componente não estejam na mesma coluna. Também não importa se o resistor está antes ou depois do LED, ele vai reduzir a corrente do laço estando antes ou depois. Veja abaixo montagem alternativa do circuito acima mas que funciona da mesma maneira. Note que o pino GND do Arduino ainda está conectado no negativo do LED e o pino 11 ainda está no positivo do LED.

## Programa: Projeto 1 - Pisca-Pisca

Primeiramente vamos explicar um programa em partes e logo mais abaixo você verá um programa completo.

A primeira coisa que fazemos no início do programa é colocar uma pequena observação sobre o nome do programa, sua função e quem o criou:

```c
// Programa : Pisca pisca
// Autor : Code Project
```

Comece uma linha com barras duplas “// ” e tudo o que vier depois nessa linha será tratado como um comentário.

Após os comentários, vem a estrutura do setup(). É nela que definimos que o pino 11 do Arduino será utilizado como saída, para servir como fonte de energia para o circuito.

```c
void setup() {
  //Define a porta do led como saida
  pinMode(11, OUTPUT);
}
```

Por último, temos o loop(), que contém as instruções para acender e apagar o LED, e também o intervalo entre essas ações:

```c
void loop() {
  //Acende o led
  digitalWrite(11, HIGH);
   
  //Aguarda intervalo de tempo em milissegundos
  delay(1000);
   
  //Apaga o led
  digitalWrite(11, LOW);
   
  //Aguarda intervalo de tempo em milissegundos
  delay(1000);
}
```

A linha do código contendo digitalWrite(11, HIGH);, liga o pino 11, acendendo o led. O comando delay(1000);, especifica o intervalo, em milésimos de segundos (milissegundos), no qual o programa fica parado antes de avançar para a próxima linha. Quanto maior esse número, mais tempo o programa vai esperar para passar para a próxima linha.

O comando digitalWrite(11, LOW);, apaga o LED, desligando o pino 11, e depois ocorre uma nova parada (delay) no programa. Após essa espera, o processo é então reiniciado, voltando para o início do loop().

Você reparou que todo comando termina com um ponto e vírgula “;“? Ele é muito importante na programação porque define que o comando acabou ali. Se está faltando um “;” o programa não irá funcionar de jeito nenhum!

Abaixo você encontra o programa completo que pode ser copiado e colado direto na IDE Arduino:

```c
// Programa : Pisca Pisca pisca
// Autor : Code Project
 
void setup() {
  //Define a porta do led como saida
  pinMode(11, OUTPUT);
}
 
void loop() {
  //Acende o led
  digitalWrite(11, HIGH);
   
  //Aguarda intervalo de tempo em milissegundos
  delay(1000);
   
  //Apaga o led
  digitalWrite(11, LOW);
   
  //Aguarda intervalo de tempo em milissegundos
  delay(1000);
}
```

## Desafios

Veja abaixo alguns desafios que você pode tentar!

* Troque o LED por outro de cor diferente;
* Monte o circuito de uma maneira alternativa usando outros furos e posições na protoboard;
* Mude o intervalo de tempo que o LED pisca mudando o valor na programação na linha delay(1000); por exemplo: delay(250).