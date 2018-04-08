<html>
<head>
</head>
<body>
<h1>작품소개</h1>
 <p>거북이 캐릭터인 꼬부기를 프로세싱을 이용하여 만든 작품입니다.</p>
 <p>거북이를 그리는 drawTurtle이라는 함수를 따로 만들어서 그렸습니다.</p>
 <p>drawTurtle 함수의 파라미터 값을 변화하여 거북이의 위치, 크기를 조정할 수 있습니다.</p> 
 
/*
function :  draw turtle
x, y : position of turtle
*/

function setup() {
  createCanvas(700, 500);
  background(255);
}

function draw(){
  drawTurtle(350, 250 , 150);
}

function drawTurtle( x, y, size) {
    //body-1
  fill(255);
  ellipse(x, y+size*0.7, size*1.3, size*1.1);

  //arms
  stroke(0);
  fill(191, 253, 255);
  bezier(x, y+size*0.5, x-size*0.3, y+size*0.3, x-size*0.5, y+size*0.05, x-size*0.95, y+size*0.05);
  bezier(x-size*0.95, y+size*0.05, x-size*0.85, y+size*0.5, x-size*0.4, y+size*0.6, x, y+size*0.5);
  bezier(x, y+size*0.5, x+size*0.3, y+size*0.3, x+size*0.5, y+size*0.05, x+size*0.95, y+size*0.05);
  bezier(x+size*0.95, y+size*0.05, x+size*0.85, y+size*0.5, x+size*0.4, y+size*0.6, x, y+size*0.5);
  
  //legs
  quad(x-size*0.01, y+size, x-size*0.5, y+size, x-size*0.3, y+size*1.6, x-size*0.01, y+size*1.6);
  quad(x+size*0.01, y+size, x+size*0.5, y+size, x+size*0.3, y+size*1.6, x+size*0.01, y+size*1.6);
  
  
  //body-2
  fill(255, 248, 162);
  arc(x, y+size*0.8, size*1.18, size, radians(0), radians(180) );
  arc(x, y+size*0.8, size*1.18, size*1.5, radians(180), radians(360));
  noFill();
  stroke(0, 0, 0);
  line(x, y+size/2, x, y+size*1.1);
  line(x, y+size*1.1, x-size/4.5, y+size*1.25);
  line(x, y+size*1.1, x+size/4.5, y+size*1.25);
  bezier( x-size/2, y+size/2.5, x-size/4, y+size/1.9, x+size/4, y+size/1.9, x+size/2, y+size/2.5);
  bezier( x-size/3, y+size*0.85, x-size/5, y+size*0.9, x+size/5, y+size*0.9, x+size/3, y+size*0.85);
  line(x-size/3, y+size*0.85, x-size/1.75, y+size*0.6); 
  line(x-size/3, y+size*0.85, x-size/1.8, y+size);
  line(x+size/3, y+size*0.85, x+size/1.75, y+size*0.6); 
  line(x+size/3, y+size*0.85, x+size/1.8, y+size);
   
  
  //head
  fill(191, 253, 255);
  ellipse(x, y, size*0.9, size/1.3);
  
  //eyes
  fill(255);
  arc(x-size/4, y-size*0.035, size*0.2, size*0.31, radians(150), radians(385), CHORD);
  arc(x+size/4, y-size*0.035, size*0.2, size*0.31, radians(155), radians(390), CHORD);
  fill(0);
  arc(x-size/4.2, y-size*0.045, size*0.17, size*0.32, radians(145), radians(390), CHORD);
  arc(x+size/4.2, y-size*0.045, size*0.17, size*0.32, radians(150), radians(395), CHORD);
  fill(255);
  ellipse(x-size/4.3, y-size*0.15, size/10.5, size/10.5);
  ellipse(x+size/4.3, y-size*0.15, size/10.5, size/10.5);
  fill(139, 34, 35);
  arc(x-size/4.2, y+size*0.009, size*0.17, size*0.2, radians(150), radians(385), CHORD);
  arc(x+size/4.2, y+size*0.009, size*0.17, size*0.2, radians(155), radians(390), CHORD);
  fill(0);
  ellipse(x-size/4.2, y-size*0.05, size/10.5, size/10.5);
  ellipse(x+size/4.2, y-size*0.05, size/10.5, size/10.5);
  
  //eyebrow
  fill(0);
  bezier(x-size/5.5, y-size*0.23, x-size/6.1, y-size*0.22, x-size/6.2, y-size*0.21, x-size/6.5, y-size*0.2);
  bezier(x+size/5.5, y-size*0.23, x+size/6.1, y-size*0.22, x+size/6.2, y-size*0.21, x+size/6.5, y-size*0.2);
  
  //nose
  strokeWeight(2);
  point(x-size*0.05, y+size*0.055);
  point(x+size*0.05, y+size*0.055);
  
  //mouth
  noFill();
  fill(0);
  bezier(x, y+size*0.1, x-size*0.1, y+size*0.07, x-size*0.15, y+size*0.12, x-size*0.4, y+size*0.1);
  bezier(x, y+size*0.1, x+size*0.1, y+size*0.07, x+size*0.15, y+size*0.12, x+size*0.4, y+size*0.1);
  
  arc(x, y+size*0.1, size*0.75, size*0.47, radians(0), radians(180));
  noStroke();
  fill(216, 129, 142, 200);
  ellipse( x, y+size*0.23, size*0.6, size*0.16);
  fill(250, 109, 130); 
  ellipse( x, y+size*0.26, size*0.5 ,size*0.15);
}
