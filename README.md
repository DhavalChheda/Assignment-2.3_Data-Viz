# Assignment-2.3_Data-Viz
Table PopulationData;
PFont labelFont;
PFont stateFont;


void setup() {
  size(600, 600);
  labelFont = loadFont("Calibri-48.vlw");
  PopulationData = new Table();
  PopulationData = loadTable("india_pop.csv", "header");
  println(PopulationData.getRowCount() + " total rows in table");
}

void draw() {
  smooth();
  background(153);
  textFont(labelFont);
  strokeWeight(1);
  stroke(19, 116, 144);
  strokeWeight(3);
  fill(250);
  textAlign(LEFT);


  textAlign(CENTER);
  rectMode(CORNER);
  rect(0, 50, width, 10);
  rect(50, 0, 10, height);
  //line(0,50,width,50);
  //line(50,0,50,1000);

  strokeWeight(5);
  stroke(27, 91, 125, 100);
  for (int i = 150; i < 550; i+=100) {
    line(i, 50, i, 1000);
    
    fill(19, 116, 144);
    textSize(20);
    fill(250, 100);
    text(i/10, i, 40);
    textSize(20);


    //println(i);
  }

  for (int b = 0; b<1050; b+=50) {
    fill(250, 100);
    text(b-50, 25, b);
    textAlign(CENTER);
    textSize(20);
    fill(199, 228, 237, 10);
  }

  smooth();
  noStroke();

  for (TableRow row : PopulationData.rows ()) {


    int    density =   (row.getInt("7"));
    int    decaGrowth = ((row.getInt("8"))*10)+50;
    int    statePopulation = (row.getInt("3"))/1000000;

    fill(250, 240, 245, 160);
    ellipse(decaGrowth, density, 20, 20);
  }


  
  }

