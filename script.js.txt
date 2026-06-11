let current = 0;

const slides = document.getElementById("slides");

setInterval(() => {
    current++;

    if(current > 2){
        current = 0;
    }

    slides.style.transform =
        `translateX(-${current * 100}%)`;

},3000);

function openLetter(){

    const letter =
    document.getElementById("letter");

    if(letter.style.display === "block"){
        letter.style.display = "none";
    }else{
        letter.style.display = "block";
    }
}

function createPetal(){

    const petal =
    document.createElement("div");

    petal.classList.add("petal");

    petal.innerHTML="🌸";

    petal.style.left =
    Math.random()*100+"vw";

    petal.style.animationDuration =
    3 + Math.random()*5 + "s";

    document.body.appendChild(petal);

    setTimeout(()=>{
        petal.remove();
    },8000);
}

setInterval(createPetal,300);