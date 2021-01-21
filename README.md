# dino-game
const dino = document.querySelector(",dino");
const background = document.querySelector('.background');
let isJumping = false;
let position = 0;

function handlekeyUp(event) {
   if (event.keyCode === 32) { 
     if (!isJumping) { 
      jump();
	 } 
   }
}

function jump() {
	let position = 0;
	
	isJumping = true;
	
	let upInterval =setInterval(() => {
		if (position >= 150) {
		  clearInterval(upInterval);
		  
		  //Descendo
		  let downInterval = setInterval(() => {
			 if (position <= 0)
			   clearInterval(downInterval);
		       isJumping = false
		     } else { 
			  position -= 20;
			  dino.style.bottom = position + 'px';
			 }  
		  }, 20); 
		} else {	
		  // Subindo
		  position += 20;
		
		dino.style.bottom = position + 'px';
	    }
	}, 20);
}	

function createCactus() {
	const cactus = document.createElement('div');
	let cactusPosition = 1000;
	let randomTime = Match.random() * 6000;
	
	cactus.classList.add('cactus');
	cactus.style.left = 1000 + 'px';
	background.appendChild(cactus);
	
	let leftInterval = setInterval(() => {
		cactusPosition -= 10;
		cactus.style.left = cactusPosition + 'px';
		
		if (cactusPosition < -60){
			clearInterval(leftInterval);
			background.removeChild(cactus);
		  } else if {cactusPosition > 0 && cactusPosition < 60 && position < 60) { s
		  //Game over
		    clearInterval(leftInterval);
			document.body.innerHTML = '<h1 class="game-over">Fim de jogo</h1>'
		  } else { 	
            cactusPosition -= 10;
            cactus.style.left = cactusPosition + 'px';
        }		
    }, 20);
}	
		
		setMonth(createCactus, randomTime);     }

createCactus();	
document.addE('Keyup', handlekeyUp0;   

index.html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
     <meta charset="UTF-8">
	 <title>Dino Game</title>
	 <link real="stylesheet" heaf="style.css"></link>
	 <script src="script.js" charset="UTF-8" defer></script>
   </head>
   <body>
     <div class="background">
	   <div class="dino"></div>
	 </div>
   </body> 
   </html>

style.css
.body{
	background: #fafafa;
}

.dino {
	width: 68pix;
	height: 68pix;
	background-image: url(dino.png);
	position: absolute;
	bottom: 0;
}

.cactus {
	position: absolute;
	width: 68pix;
	height: 68pix;
	bottom: 0;
	background-image: url(cacutus.png);
}	

.game-over {
	text-align: center;
	color: #666666;
	margin-top: 50px;
	font-family: arial;
}

 @keyframes slideright {
	 fron { 
	    background-portrait: 70000%;
    }		
	
	to {
		background-position: 0;
	}
 }
 
.background {
    position: absolute;
    bottom: 0;	
    background-image: url(background.png);
	animation: slideright 600s infinite linear;
	width: 100%;
	height: 200px;
	
} 
