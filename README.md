# Webdev-Task-2-game-0
HACKER MODE : 1. the game ends on being hit by projectiles or being squished bt walls 2.sounds added 
<!DOCTYPE html>

<html>

<head>

<title>
Task 2 game
</title>

<style>
</style>
</head>
<body style="background-color:black;">

<canvas id="game" height="525" width="1070" style="border:3px solid #000010;" onmousemove="showCoords(event)">
</canvas>

<script>

var x,y,a=50,pxy=1000,d=0,i=0,k=0,pyx=1500,b=10,h,m,oddr,pz=1200,r;
var mySound;
mySound = new sound("carcrash.mp3");
var c = document.getElementById("game");
var ctx = c.getContext("2d");
function showCoords(event) 
{ if((Math.abs(x-pyx)<20)&&(y>500-b)||((Math.abs(x-pxy)<20)&&(y<a)))
 {y = event.clientY;
  if(event.clientX<x)
   x = event.clientX; 
  else
   x--;

    }
    else
 {setInterval(varfollo,1);}
var varfollo=function()
{
 if(y==event.clientY)
 {d=1;}
 else
 if(y>event.clientY)
 y--;
 else
 if(y<event.clientY)
 y++;
 if(x==event.clientX)
 {d=1;}
 else
 if(x>event.clientX)
 x--;
 else
 if(x<event.clientX)
 x++;
 

}

}

 var lastr1=function()
{

ctx.fillStyle="white";
ctx.fillRect(0,0,1070,525);
 for(m=0;m<9;m++)
 {
 ctx.fillStyle="brown";
 ctx.fillRect(1020,(m+1)*50,50,20);
 m++;
 }

 for(h=0;h<100;h++)
 { 
 ctx.moveTo(0,h*10);
 ctx.lineTo(10,(h+1)*10);
 ctx.stroke();
 ctx.moveTo(10,(h+1)*10);
 ctx.lineTo(0,(h+2)*10);
 ctx.stroke();
 h++;
 }

 ctx.moveTo(171, 0);
 ctx.lineTo(171,525);
 ctx.stroke();
 ctx.moveTo(0,500);
 ctx.lineTo(1070,500);
 ctx.stroke();
 ctx.fillStyle = "red"; 
 ctx.font = "30px Helvetica";
 ctx.fillText("game arena",1,520);   
 ctx.fillText("Run barry!!Run!!",171,520);    


{
if(x<10)
x=10; 
}
{
if(x>150)
x=150;
}
ctx.beginPath();
ctx.arc(x,y,20,0,2*Math.PI);
ctx.fillStyle="black";
ctx.fill();
ctx.stroke();
if(pxy>0)
pxy--;
else
{i++;
pxy=1000;
a= Math.floor((Math.random()*456)+ 0); 
}
if(pyx>0)
pyx--;
else
{i++;
pyx=1000;
b= Math.floor((Math.random()*456)+ 0); 
}
if(pz>0)
{pz--;
}
else
{
r= Math.floor((Math.random()*4)+ 0); 
oddr=2*r+1;
pz=1200;
fif_oddr=50*oddr;
}
ctx.fillStyle="rgb(0,200,0)";
ctx.fillRect(pxy,0,10,a);
//ctx.fillRect(pxy,500-a,10,500-a);//
//ctx.fillRect(pyx,0,10,b);//
ctx.fillRect(pyx,500-b,10,500);

ctx.fillStyle="red";
ctx.fillRect(pz,oddr_update(),10,10);

if((Math.abs(x-pyx)<20)&&(y>500-b)||((Math.abs(x-pxy)<20)&&(y<a)))
{
x--;
}
if((Math.abs(x-pz)<20)&&((y>fif_oddr)&&(y<(fif_oddr+10)))||(x==20))
{clearInterval(tonystank);
ctx.fillStyle="white";
ctx.fillRect(0,0,1070,525);
ctx.fillStyle = "red"; 
ctx.font = "30px Helvetica";
ctx.fillText("sorry !! game over",500,250);
ctx.fillText("score :"+i,1,520);
mySound.play();
}
}
var tonystank=setInterval(lastr1,1);
function oddr_update()
{if((pz<1020)&&(pz>600))
{fif_oddr--;
}
else{
if(pz<600)
fif_oddr++;}
return fif_oddr;
}
function restart()
{
var tonystank=setInterval(lastr1,1);
}
function sound(src) {
    this.sound = document.createElement("audio");
    this.sound.src = src;
    this.sound.setAttribute("preload", "auto");
    this.sound.setAttribute("controls", "none");
    this.sound.style.display = "none";
    document.body.appendChild(this.sound);
    this.play = function(){
        this.sound.play();
    }
    this.stop = function(){
        this.sound.pause();
    }    
}
</script>
<form>
<button onclick="restart()">Restart</button>
</form>
</body>
</html>
