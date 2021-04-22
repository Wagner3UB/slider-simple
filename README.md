Slider simples em JQuery tirado do site http://responsiveslides.com/

Instalação:

1- criar o arquivo JS chamado responsiveslides.min.js - atenção para oendereço (js/ ou direto na raiz)
2- criar estrutura basica para o slider no DOM:

  <ul class="rslides">
    <li><img src="img/slide1.png" alt=""></li>
    <li><img src="img/slide2.png" alt=""></li>
    <li><img src="img/slide3.png" alt=""></li>
    <li><img src="img/slide4.png" alt=""></li>
    <li><img src="img/slide5.png" alt=""></li>
  </ul>

3- criar estrutura basica no CSS, prestando atenção na classe colocada na lista.
*Neste caso coloquei um slider com 100% da tela em que existia uma divisão em grid
**É responsivo com imagens baixas, pode não ser bonito visivelmente em mobiles

.rslides {
  grid-column: 1/5;
  position: relative;
  list-style: none;
  overflow: hidden;
  width: 100%;
  padding: 0;
  margin: 0;
}

.rslides li {
  position: absolute;
  display: none;
  width: 100%;
  left: 0;
  top: 0;
}

.rslides li:first-child {
  position: relative;
  display: block;
  float: left;
}

.rslides img {
  display: block;
  height: auto;
  float: left;
  width: 100%;
  border: 0;
}

/* Arrows */

.rslides_nav {
  position: absolute;
  z-index: 9;
  top: 200px;
  margin-top: -25px;
  width: 50px;
  height: 50px;
  background-color: #ffffff;
  color: #000;
  font-size: 20px;
  text-transform: uppercase;
  line-height: 50px;
  text-align: center;
  border-radius: 5px;
  opacity: 0.8;
  transition: all .3s linear;
}
.rslides_nav:hover {
  opacity: 1;
}
.prev {
  left: 20px;
}
.next {
  right: 20px;
}

4- acrescentar o init dentro de um script ao finalizar o body - Cuidar com o nome da classe e as opções

  <script>
    $(function() {
      $(".rslides").responsiveSlides({
        nav: true,
        prevText: "⮜",
        nextText: "⮞"
      });
    });
  </script>

5- Adicionar as imagens com nomes iguais as da lista (img/slideX.png)
*Manter proporções entre as imagens



EXTRA: Slider options

$(".rslides").responsiveSlides({
  auto: true,             // Boolean: Animate automatically, true or false
  speed: 500,            // Integer: Speed of the transition, in milliseconds
  timeout: 4000,          // Integer: Time between slide transitions, in milliseconds
  pager: false,           // Boolean: Show pager, true or false
  nav: false,             // Boolean: Show navigation, true or false
  random: false,          // Boolean: Randomize the order of the slides, true or false
  pause: false,           // Boolean: Pause on hover, true or false
  pauseControls: true,    // Boolean: Pause when hovering controls, true or false
  prevText: "Previous",   // String: Text for the "previous" button
  nextText: "Next",       // String: Text for the "next" button
  maxwidth: "",           // Integer: Max-width of the slideshow, in pixels
  navContainer: "",       // Selector: Where controls should be appended to, default is after the 'ul'
  manualControls: "",     // Selector: Declare custom pager navigation
  namespace: "rslides",   // String: Change the default namespace used
  before: function(){},   // Function: Before callback
  after: function(){}     // Function: After callback
});

