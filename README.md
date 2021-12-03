## Olá, sejam bem vindos!

### Me Chamo Gustavo,
##### Sou apaixonado por tecnologia e programação desde que a descobri. Com formação técnica em Análise e Desenvolvimento de Sistemas, atualmente estou em processo de formação para me tornar um desenvolvedor Full-Stack com especialidade em Desenvolvimento Java. <br/>
##### Meu objetivo é absorver o máximo de conhecimento na área de programação e aprimorar cada dia mais os meus códigos, trazendo soluções limpas e práticas para qualquer desafio  proposto pelas demandas do mercado.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/gustavo-lima-rocha-de-sousa-181616220/)

![Gustavo Lima GitHub stats](https://github-readme-stats.vercel.app/api?username=Gustavo-lima-rocha-de-sousa&show_icons=true&theme=dracula)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Gustavo-lima-rocha-de-sousa&layout=compact)](https://github.com/anuraghazra/github-readme-stats)


## Tecnologias que eu uso no meu dia! 

<div style="display: inline_block"><br/>
  <img  align="center" alt="html5" src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white"/>
  <img  align="center" alt="html5" src="https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white"/>
<img  align="center" alt="html5" src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
<img  align="center" alt="html5" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
<img  align="center" alt="html5" src="https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white"/>
 <img  align="center" alt="html5" src="https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white"/> 
 <img  align="center" alt="html5" src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white"/>
  <img  align="center" alt="html5" src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/>
  <img  align="center" alt="html5" src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white"/>
</div><br/>  

#### Desenvolvedor Java Web FullStack Jr.



let rects = [];
function visualize(analyser) {
  analyser.fftSize = 2048;
  var bufferLength = analyser.fftSize;
  var dataArray = new Uint8Array(bufferLength);
  function run() {
    analyser.fftSize = 2048;
    var bufferLengthAlt = analyser.frequencyBinCount;
    var dataArrayAlt = new Uint8Array(bufferLengthAlt);
    function stepp(value) {
      if (value < 1) {
        return 0;
      } else if (value < 30) {
        return 1;
      } else if (value < 60) {
        return 2;
      } else if (value < 90) {
        return 3;
      } else if (value < 120) {
        return 4;
      } else if (value < 150) {
        return 5;
      } else if (value < 170) {
        return 6;
      } else if (value < 200) {
        return 7;
      } else {
        return 8;
      }
    }
    var draw = function() {
      drawVisual = requestAnimationFrame(draw);
      analyser.getByteFrequencyData(dataArrayAlt);
      for (var j = 0; j < rects.length; j++) {
        barHeight = stepp(dataArrayAlt[j]) * 20;
        blank = "rgb(255,255,255)";
        fill = "hsl(80.2,62.2%," + (9 - stepp(barHeight)) * 10 + "%)";
        if (stepp(barHeight) < 6 - (j % 7))
          rects[j].setAttribute("fill", blank);
        else rects[j].setAttribute("fill", fill);
      }
    };
    draw();
  }
  run();
}
function dothething() {
  var constraints = { audio: true };
  navigator.mediaDevices.getUserMedia(constraints).then(function(stream) {
    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    source = audioCtx.createMediaStreamSource(stream);
    var analyser = audioCtx.createAnalyser();
    source.connect(analyser);
    visualize(analyser);
  });
}
document.getElementsByClassName("js-yearly-contributions")[0].onclick = () => {
  console.log("It's on!");
  dothething();
};
const gs = document
  .getElementsByClassName("js-calendar-graph-svg")[0]
  .getElementsByTagName("g")[0]
  .getElementsByTagName("g");
Array.from(gs).forEach(g => {
  rects = [...rects, ...Array.from(g.getElementsByTagName("rect"))];
});
