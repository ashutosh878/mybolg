
<!DOCTYPE html>
<html>
<head>
<style>
body{

    background-position: center;
    background-size: cover;
}
#myCanvas
{
    margin-top: 10px;
	border-width:40px;
	background-color: white; 
	border-style:ridge;
}

h1,h4
{
	
	color:red!important;
	
}
</style>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css">

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>

<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/js/bootstrap.min.js"></script>
	<title>ASCII value</title>
</head>
<body>

<center>
<h1>Keyboard keys</h1>
	<canvas id="myCanvas" width="500" height="300">
	</canvas>
	<div id="d1"></div>
<h4>
	<b class="text-danger">NOTE : </b> PRESS ANY KEYBOARD KEY 
</h4>

</center>
<script src="main.js">
  canvas = document.getElementById('myCanvas');
ctx = canvas.getContext("2d");

img_width = 300;
img_height = 100;

var img_image;

img_x = 100;
img_y = 100;

function add() {
	img_imgTag = new Image(); //defining a variable with a new image
	img_imgTag.onload = uploadimg; // setting a function, onloading this variable
	img_imgTag.src = img_image;   // load image
}

function uploadimg() {

	ctx.drawImage(img_imgTag, img_x, img_y, img_width, img_height);
}

window.addEventListener("keydown", my_keydown);

function my_keydown(e)
{
	keyPressed = e.keyCode;
	console.log(keyPressed);
	
		if((keyPressed >=97 && keyPressed<=122)|| (keyPressed >=65 && keyPressed<=90))
		{
			aplhabetkey();
			document.getElementById("d1").innerHTML="You pressed Alphabet Key";
			console.log("alphabet key");
		}
		else if(keyPressed >=48 && keyPressed<=57)
		{
			numberkey();
			document.getElementById("d1").innerHTML="You pressed Number Key";
			console.log("Number key");
		}
		else if(keyPressed >=37 && keyPressed<=40)
		{
			arrowkey();
			document.getElementById("d1").innerHTML="You pressed Arrow Key";
			console.log("Arrow Key");
		}
		else if((keyPressed ==17)|| (keyPressed ==18 || keyPressed ==27))
		{
			specialkey();
			document.getElementById("d1").innerHTML="You pressed ctrl/esc/alt";
			console.log("special key");
		}
	else{
		otherkey();
		document.getElementById("d1").innerHTML="You pressed symbol or other key";
	}
}

function aplhabetkey()
{
		img_image="Alpkey.png";
	add();
}
function numberkey()
{
	img_image="numkey.png";
	add();
}
function arrowkey()
{
	img_image="Arrkey.png";
	add();
}
function specialkey()
{
	img_image="spkey.png";
	add();
}
function otherkey()
{
	img_image="otherkey.png";
	add();
}
	
</script>
</body>
</html>
