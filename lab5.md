
Square sq1, sq2; //Declara la variable del class

void setup() {
  size(300, 300);
  smooth();
  noStroke();
  sq1= new Square(50, 0,  80, 0.5); //Dando valor a las variables
  sq2= new Square(150, 0, 80, 1.5);
}

void draw() {
  background(0);
  sq1.move(); //COntructor de objetos
  sq2.move();
  sq1.display();
  sq2.display();
}

class Square { //Definir el Class
  float x, y, b, speed;
  int direct=1;
  Square(float xpos, float ypos, float g, float sp) { //Contructor
    x=xpos; //Asignando osicion 
    y=ypos;
    b=g;
    speed=sp; //Asignando diametro
  }
  void display() {
    rect(x, y, b, b);
  }

  void move() {
    y += (speed * direct);
    if ((y > (height - b / 2)) || (y < b / 2)) { //Movimiento de los cuadros
      direct *= 1;
      
    }  
    }
}
