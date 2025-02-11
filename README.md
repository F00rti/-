let score=0;
function getRandom(max){
    return Math.floor(Math.random()*max)
}
function createMouse(){
    const gameArea = document.getElementById("gameArea");
    const mouse = document.createElement("div");
    mouse.className = 'mouse';
    let maxWidth = gameArea.offsetWidth;
    let maxHeight = gameArea.offsetHeight;
    mouse.style.top=getRandom(maxHeight)+"px"
    mouse.style.left=getRandom(maxWidth)+"px"
mouse.onclick = function(){
    score = score+1;
    document.getElementById("score").innerHTML="Счёт: "+score;
    gameArea.removeChild(mouse);
    createMouse();
}
gameArea.appendChild(mouse);
}
createMouse()
