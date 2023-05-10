<!DOCTYPE html>
<html lang="en">

<head>
  <title>Simulation-ball_movement</title>
</head>

<body>
  <div id="ball"  style="z-index:5;
      position: absolute;
      top: 200px;
      left: 0px;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      background: rgb(23, 104, 179);">
      </div>
</body>

<script>
let velocityX= 5;
let velocityY= 5;
let positionX = 0;
let positionY = 0;
let positionxmin = 0;
let positionxmax = 250;
let positionymin = 0;
let positionymax = 250;
let time = 15;
let reverse_X = true;
let reverse_Y= true;
let ball= document.getElementById('ball');

function moveBall() {
  if(reverse_X){
    positionX = positionX + velocityX;
    ball.style.top = positionY + 'px';
    ball.style.right = positionX + 'px';
  }else{
    positionX = positionX - velocityX;
    ball.style.right = positionY + 'px';
    ball.style.top = positionX + 'px';
 }
 if(reverse_Y){
  positionY = positionY + velocityY;
  ball.style.left = positionX + 'px';
  ball.style.bottom = positionY + 'px';
}else{
  positionY = positionY - velocityY;
  ball.style.top = positionX - 'px';  
  ball.style.left = positionX + 'px';
}

 if(positionX > positionxmax || positionX === positionxmin){
    reverse_X = !reverse_X;
  }

  if(positionY > positionymax || positionY === positionymin){
    reverse_Y = !reverse_Y;
  }
}
  setInterval(moveBall, time);

</script>

</html>
