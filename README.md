var car1;
var wall1;
var speed,weight;
function setup() {
  createCanvas(1300,600);
  wall1=createSprite(1230,450,10,800);
  car1=createSprite(80,300,30,20);
  speed=random(5,15);
  weght=random(400,1500);
}

function draw() {
  background(255)
  car1.velocityX=5
  car1.collide(wall1)
  car1.velocityX=speed;
  if(wall1.x-car1.x<car1.width+wall1.width){
    car1.velocityX=0;
    var deformation=0.5*weight*speed*speed/22509
    if(deformation>180){
      car1.shapeColour=colour(255,0,0);
    }
    if(deformation<180 && deformation>100){
      car1.shapeColour=colour(230,230,0);
    }
    if(deformation<180){
      car1.shapeColour=colour(0,255,0);
    }
  }
  drawSprites();
}
