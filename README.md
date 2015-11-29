# visualizaci-n-de-datos-3D

// visualizacion 2D

//variables
Table tB;

//full color
color c1 = color(65, 63, 232);
color c2 = color(37, 212, 226);
color c3 = color(170, 9, 232);
color c4 = color(232, 0, 216);
color c5 = color(232, 4, 11);
color c6 = color(232, 165, 18);
color c7 = color(232, 224, 5); 
color c8 = color(11, 232, 60);

color x = color(0);

//tipos de letras
PFont fontR;
PFont fontR2;
PFont fontUL;
PFont fontUL2;
PFont fontUL3;
PFont fontA;


void setup() {
  size(1400, 1000, P3D);
  background(255);

  tB= loadTable ("tabla 6.4.csv", "header");

  // tipos de letras
  fontR= loadFont("TsukuARdGothic-Bold-32.vlw");
  textFont(fontR, 32);
  smooth(4);

  fontR2= loadFont("TsukuARdGothic-Regular-32.vlw");
  textFont(fontR2, 32);
  smooth(4);

  fontUL= loadFont("AvenirNext-UltraLight-32.vlw");
  textFont(fontUL, 32);
  smooth(4);

  fontUL2= loadFont("AvenirNext-UltraLight-90.vlw");
  textFont(fontUL, 90);
  smooth(3);

  fontUL3= loadFont("AvenirNext-UltraLight-18.vlw");
  textFont(fontUL, 18);
  smooth(4);  

  fontA= loadFont("ArialHebrew-Bold-180.vlw");
  textFont(fontUL, 180);
  smooth(4);
}



void draw() {
  //fondo
  background(255);
  camera(mouseX, mouseY, (height/2) / tan(PI/6), width/2, height/2, 0, 0, 1, 0);
  
  titulo();
  anos();
  convenciones();
  total();
  EDITSIV();
  EDITSIII();
  EDITSII();
  tcolum();

  ////texto de coordenadas
  //text(mouseX + " , "+ mouseY, mouseX, mouseY);
}

void titulo() {

  fill(0);
  textFont(fontR);
  text("Distribución de la inversión según grupos de", 505, 100,-300);
  text("actividades conducentes a la innovación.", 565, 140,-300);

}

void anos() {

  fill(0);
  textFont(fontUL2);
  text("2008", 200, 135,-300);
  text("2013", 210, 235,-300);
}

void convenciones() {

  fill(0);
  textFont(fontUL);
  text("Convenciones",155, 570);

//tabla de colores/convenciones
//rect(x, y, width, height)
  strokeWeight(2);
  fill(c8);
  rect(155, 590, 50, 5);
  fill(0);
  textFont(fontUL3);
  text("Maquinaria y Equipo",215, 595);

  fill(c7);
  rect(155, 620, 50, 5);
  fill(0);
  text("Investigación y Desarrollo", 215, 625);

  fill(c6);
  rect(155, 650, 50, 5);
  fill(0);
  text("Asistencia Técnica y Consultoría", 215, 655); 

  fill(c5);
  rect(155, 680, 50, 5);
  fill(0);
  text("Mercadeo de Innovaciones", 215, 685);

  fill(c4);
  rect(155, 710, 50, 5);
  fill(0);
  text("Transferencia de Tecnología", 215, 715);

  fill(c3);
  rect(155, 740, 50, 5);
  fill(0);
  text("Tecnologías de Información y Comunicaciones", 215, 745);

  fill(c1);
  rect(155, 770, 50, 5);
  fill(0);
  text("Ingeniería y Diseño Industrial", 215, 775);

  fill(c2);
  rect(155, 800, 50, 5);
  fill(0); 
  text("Formación y Capacitación", 215, 805);
} 

void total() {

  pushMatrix();
  //texto
  strokeWeight(2);
  stroke(0);
  textFont(fontR);
  fill(0);
  text(tB.getString(9, 1), 170, 357);
  text("$", 155, 357);
  //figura
  fill(255);
  //translate(x, y, z)
  translate(260, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getInt(9, 1))*10, 85);
  popMatrix(); 

}

void EDITSIV() {
//mas cercana

//rosado
  pushMatrix();
  //texto
  strokeWeight(2);
  stroke(255);
  textFont(fontUL);
  fill(x);
  text(tB.getString(4,6),380,410,300);
  text("%",400,410,300);
  //figura
  fill(c4);
  //translate(x, y, z)
  translate(400, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(4, 6))*10, 85);
  popMatrix();  

//azul  
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(6,6),480,410,300);
  text("%",500,410,300);
  //figura
  fill(c1);
  //translate(x, y, z)
  translate(500, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(6, 6))*10, 85);
  popMatrix();   

//azul claro
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(7,6),580,410,300);
  text("%",600,410,300);
  //figura
  fill(c2);
  //translate(x, y, z)
  translate(600, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(7, 6))*10, 85);
  popMatrix(); 
  
//mostaza  
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(2,6),680,385,300);
  text("%",700,385,300);
  //figura
  fill(c6);
  //translate(x, y, z)
  translate(700, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(2, 6))*10, 85);
  popMatrix();

//rojo
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(3,6),780,385,300);
  text("%",800,385,300);
  //figura
  fill(c5);
  //translate(x, y, z)
  translate(800, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(3, 6))*10, 85);
  popMatrix();

//verde
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(0,6),870,295,300);
  text("%",905,295,300);
  //figura
  fill(c8);
  //translate(x, y, z)
  translate(900, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(0, 6))*10, 85);
  popMatrix();

//morado
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(5,6),970,290,300);
  text("%",1005,290,300);
  //figura
  fill(c3);
  //translate(x, y, z)
  translate(1000, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(5, 6))*10, 85);
  popMatrix();   

//amarillo
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(1,6),1070,240,300);
  text("%",1105,240,300);
  //figura
  fill(c7);
  //translate(x, y, z)
  translate(1100, 431, 300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(1, 6))*10, 85);
  popMatrix();

}

void EDITSIII() {

//centro

//rosado
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(4,5),380,410);
  text("%",400,410);
  //figura
  fill(c4);
  //translate(x, y, z)
  translate(400, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(4, 5))*10, 85);
  popMatrix();  

//azul claro
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(7,5),480,410);
  text("%",500,410);
  //figura
  fill(c2);
  //translate(x, y, z)
  translate(500, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(7, 5))*10, 85);
  popMatrix(); 

//azul
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(6,5),580,385);
  text("%",600,385);
  //figura
  fill(c1);
  //translate(x, y, z)
  translate(600, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(6, 5))*10, 85);
  popMatrix();   

//mostaza 
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(2,5),680,370);
  text("%",700,370);
  //figura
  fill(c6);
  //translate(x, y, z)
  translate(700, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(2, 5))*10, 85);
  popMatrix();

//rojo 
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(3,5),780,370);
  text("%",800,370);
  //figura
  fill(c5);
  //translate(x, y, z)
  translate(800, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(3, 5))*10, 85);
  popMatrix();

//amarillo
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(1,5),870,310);
  text("%",905,310);
  //figura
  fill(c7);
  //translate(x, y, z)
  translate(900, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(1, 5))*10, 85);
  popMatrix();

//morado
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(5,5),970,295);
  text("%",1005,295);
  //figura
  fill(c3);
  //translate(x, y, z)
  translate(1000, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(5, 5))*10, 85);
  popMatrix(); 

//verde
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(0,5),1070,242);
  text("%",1105,242);
  //figura
  fill(c2);
  //translate(x, y, z)
  translate(1100, 431, 0);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(0, 5))*10, 85);
  popMatrix();

}


void EDITSII() {

//fondo
//rosado
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(4,4),390,410,-300);
  text("%",400,410,-300);
  //figura
  fill(c4);
  //translate(x, y, z)
  translate(400, 431, -300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(4, 4))*10, 85);
  popMatrix();  

//azul
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(6,4),480,410,-300);
  text("%",500,410,-300);
  //figura
  fill(c1);
  //translate(x, y, z)
  translate(500, 431, -300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(6, 4))*10, 85);
  popMatrix();   

//
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(7,4),580,410,-300);
  text("%",600,410,-300);
  //figura
  fill(c2);
  //translate(x, y, z)
  translate(600, 431, -300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(7, 4))*10, 85);
  popMatrix(); 

//mostaza  
 pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(2,4),680,370,-300);
  text("%",700,370,-300);
  //figura
  fill(c6);
  //translate(x, y, z)
  translate(700, 431, -300);
  ////rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(2, 4))*10, 85);
  popMatrix();

//rojo
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(3,4),770,360,-300);
  text("%",805,360,-300);
  //figura
  fill(c5);
  //translate(x, y, z)
  translate(800, 431, -300);
  ////rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(3, 4))*10, 85);
  popMatrix();

//amarillo
pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(1,4),870,335,-300);
  text("%",905,335,-300);
  //figura
  fill(c7);
  //translate(x, y, z)
  translate(900, 431, -300);
  ////rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(1, 4))*10, 85);
  popMatrix();

//morado  
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(5,4),970,280,-300);
  text("%",1005,280,-300);
  //figura
  fill(c3);
  //translate(x, y, z)
  translate(1000, 431, -300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(5, 4))*10, 85);
  popMatrix();   

//verde
  pushMatrix();
  //texto
  strokeWeight(2);
  textFont(fontUL);
  fill(x);
  text(tB.getString(0,4),1070,235,-300);
  text("%",1105,235,-300);
  //figura
  fill(c8);
  //translate(x, y, z)
  translate(1100, 431, -300);
  //rotateY(0.5);
  //box(width, height, depth)
  box(85, (tB.getFloat(0, 4))*10, 85);
  popMatrix();

}

void tcolum() {
  fill(0);
  textFont(fontUL3);
  textSize(16);
  text("Gran Total",223,436,43);
  textFont(fontUL3);
  text("EDITSII: 2008-2009",1020,640,-300);
  text("EDITSIII: 2010-2011",1020,650);
  text("EDITSIV: 2012-2013",1020,660,300);
}
