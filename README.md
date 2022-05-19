//variáveis da bolinha
2
let xBolinha = 300;
3
let yBolinha = 200;
4
let diametro = 13;
5
let raio = diametro / 2 ;
6
7
//velocidade da bolinha
8
let velocidadeXBolinha = 6;
9
let velocidadeYBolinha = 6;
10
let raqueteComprimento = 10;
11
let raqueteAltura = 90;
12
13
//variáveis da raquete
14
let xRaquete = 5;
15
let yRaquete = 150;
16
17
//variáveis do oponente
18
let xRaqueteOponente = 585;
19
let yRaqueteOponente = 150;
20
let velocidadeYOponente;
21
22
let colidiu = false;
23
24
//placar do jogo
25
let meusPontos = 0;
26
let pontosDoOponente = 0;
27
28
//sons do jogo
29
let ponto;
30
let raquetada;
31
let trilha;
32
33
function preload(){
34
  trilha = loadSound("trilha.mp3");
35
  raquetada = loadSound("raquetada.mp3");
36
  ponto = loadSound("ponto.mp3");
37
}
38
39
function setup() {
40
  createCanvas(600, 400);
41
  trilha.loop();
42
}
43
44
function draw() {
45
  background(0);
46
  mostraBolinha();
47
  movimentaBolinha();
48
  verificaColisaoBorda();
49
  mostraRaquete(xRaquete, yRaquete);
50
  movimentaMinhaRaquete();
51
  //verificaColisaoRaquete();
52
  verificaColisaoRaquete(xRaquete, yRaquete);
53
  mostraRaquete(xRaqueteOponente, yRaqueteOponente);
54
  movimentaRaqueteOponente();
