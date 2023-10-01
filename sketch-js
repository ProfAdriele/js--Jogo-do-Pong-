// criação das variáveis:// sempre escreva o let na frente das variáveis;
// variáveis da bolinha
let xbolinha = 300;
let ybolinha = 200;
let diametro = 13;
let raio = diametro / 2;

//velocidade da bolinha 
let velocidadeXbolinha = 5;
let velocidadeYbolinha = 5;

//variáveis da raquete
let xRaquete = 5; // posição x da raquete
let yRaquete = 150; // posição y da raquete
let raqueteComprimento = 10; //da raquete
let raqueteAltura = 90;

// criação das variáveis da raquete do oponente
let xRaqueteOponente = 585;
let yRaqueteOponente = 150;

let colidiu = false;

// placar do jogo
let meusPontos = 0;
let pontosDoOponente = 0;

//sons do jogo
let raquetada;
let trilha;
let ponto;

function preload(){
  raquetada = loadSound("raquetada.mp3");
  trilha = loadSound ("trilha.mp3")
  ponto = loadSound ("ponto.mp3");
}

function setup() {
  createCanvas(600, 400);
  trilha.loop();
  }

// } indica fim
function draw() {
  background("purple");
  mostrabolinha();
  verificaColisaoBorda();
  movimentabolinha(); // sempre chamar a função no draw;

  mostrarRaquete();
  movimentaMinhaRaquete();
  verificaColisãoRaquete();

  // raquete do oponente
  mostraRaqueteOponente();
  movimentaRaqueteOponente();
  verificaColisaoRaqueteOponente;
  incluiPlacar();
  marcaponto();
}

function mostrabolinha() {
  circle(xbolinha, ybolinha, diametro);
  xbolinha += velocidadeXbolinha;
  ybolinha += velocidadeYbolinha;
}

function movimentabolinha() {
  xbolinha = xbolinha + velocidadeXbolinha;
  ybolinha = ybolinha + velocidadeYbolinha;
}
function verificaColisaoBorda() {
  if (xbolinha > width || xbolinha < 0) {
    velocidadeXbolinha *= -1;
  }

  if (ybolinha > height || ybolinha < 0) {
    velocidadeYbolinha *= -1;
  }
}
// lugar do SE de condição, usar o IF; (AULA 2- ALURA- VÍDEO 4
// criar uma nova função chamada  mostrar raquete
function mostrarRaquete() {
  rect(xRaquete, yRaquete, raqueteComprimento, raqueteAltura);
}
//editor.p5js.org/Adrielee01/sketches/sGFVfh6nZ

 function movimentaMinhaRaquete() {
  if (keyIsDown(UP_ARROW)) {
    yRaquete -= 10;
  }
  if (keyIsDown(DOWN_ARROW)) {
    yRaquete += 10;
  }
}

function verificaColisãoRaquete() {
  if (
    xbolinha - raio < xRaquete + raqueteComprimento &&
    ybolinha - raio < yRaquete + raqueteAltura &&
    ybolinha + raio > yRaquete
  ) {
    velocidadeXbolinha *= -1;
    raquetada.play();
  }
}
// raquete do oponente
function mostraRaqueteOponente() {
  rect(xRaqueteOponente, yRaqueteOponente, raqueteComprimento, raqueteAltura);
}

function movimentaRaqueteOponente() {
   if (keyIsDown(87)) {
    yRaqueteOponente -= 10;
  }
  if (keyIsDown(83)){
    yRaqueteOponente += 10;

  }
}

function verificaColisaoRaqueteOponente() {
  colidiu = collideRectCircle(
    xRaqueteOponente,
    yRaqueteOponente,
    raqueteComprimento,
    raqueteAltura,
    xbolinha,
    ybolinha,
    raio
  );
  if (colidiu == true) {
    velocidadeXbolinha += -1;
    raquetada.play();
  }
}
// Placar
function incluiPlacar() {
  stroke(255);
  textAlign(CENTER);
  textSize(16);
  fill(color(238, 130, 230));
  rect(150, 10, 40, 20);
  fill(255);
  text(meusPontos, 170, 26);
  fill(color(238, 130, 230));
  rect(450, 10, 40, 20);
  fill(255);
  text(pontosDoOponente, 470, 26);
}
//marcar ponto
function marcaponto() {
  if (xbolinha > 590) {
    meusPontos += 1;
    ponto.play();
  }
  if (xbolinha < 10) {
    pontosDoOponente += 1;
    ponto.play();
  }
}
