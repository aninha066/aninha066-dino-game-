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
