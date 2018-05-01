<template>
  <div id="app">
      <div v-show="loading" id="preloader">
        <img src="static/loader/loader.gif" />
      </div>
      <div id="board" style="left: 0px;">
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">AFI's 100 year...100 movies</h2>
              <br />
              <p class="chapterText">AFI : 100 ans... 100 films</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">L'AFI</h2>
              <p class="chapterText">L'American Film Institute a établi en 1998 une première liste des 100 meilleurs films américains du siècle. Cette liste a été mise à jour 10 ans plus tard.</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">400 films</h2>
              <p class="chapterText">ont été pré-sélectionnés.</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">+ de 1500 votants</h2>
              <p class="chapterText">faisant partie du monde du cinéma américain ont été interrogés.</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">100 longs métrages</h2>
              <p class="chapterText">Des films de plus de 60 minutes minimum.</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">100 films américains</h2>
              <p class="chapterText">dont la production, distribution ou réalisation est principalement américaine.</p>
            </div>
          </div>
          <div class="board__slide">
            <img src="static/images/rideaurouge.png" />
            <div class="vertically-centered">
              <h2 class="chapterTitle">100 films cultes</h2>
              <p class="chapterText">qui ont reçu des récompenses et un bel accueil critique mais également marqué la culture populaire.</p>
            </div>
          </div>
          <!--Les débuts-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">20s</h2>
              <p class="chapterText">Dans les années 20 le cinéma Hollywoodien explose. Les Américains ont du temps pour s'amuser et vont régulièrement dans les salles. Les acteurs deviennent de véritables stars. Charlie Chaplin en est le meilleur exemple.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(0, 4)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--30's 5-16-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">30s</h2>
              <p class="chapterText">Le cinéma parlant apparu en 1927 prend de l'ampleur au cours de cette décennie. La crise  de 1929 a également son influence dans les sujets traités par les films beaucoup plus sociaux que par le passé. On retrouve notamment la critique du Taylorisme dans <em>les Temps Modernes</em> de Chaplin. Il est d'ailleurs le dernier réalisateur pouvant se permettre de faire du muet.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(5, 16)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--40's 16-27-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">40s</h2>
              <p class="chapterText">Le cinéma des années 40 s'est perfectionné techniquement parlant après la transition non sans embûche vers le cinéma parlant de la décennie précédente. La guerre a cependant ralenti l'exportation des films à l'étranger.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(16, 27)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--50's 27-43-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">50s</h2>
              <p class="chapterText">Les années 50 ont connu la naissance du Rock'n'Roll et Hollywood s'est adapté à son nouveau public en développant stars dans des rôles d'antihéros comme Marlon Brando dans <em>Un Tramway nommé Désir</em>.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(27, 43)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--60's 43-60-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">60s</h2>
              <p class="chapterText">Les années 60 sont des années de transition pour le cinéma hollywoodien qui rentre en concurrence avec la télévision et qui connait certaines difficultées fiancières. Les films en couleur se démocratisent vraiment pour se démarquer et éblouir les spectateurs.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(43, 60)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--70's 60-80-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">70s</h2>
              <p class="chapterText">C'est la décennie du nouvel hollywood qui a vu émerger des réalisateurs comme Spielberg, George Lucas ou Scorsese. C'est un cinéma qui s'inspire de l'Europe entre la nouvelle  vague française et le néo-réalisme italien.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(60, 80)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--80's 80-88-->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">80s</h2>
              <p class="chapterText">Les années 80 marquent le début du numérique et des films à très gros budgets calibrés pour marcher: les Blockbusters. La science-fiction est un genre qui prédomine avec <em>Blade Runner</em> et <em>E.T.</em> notamment.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(80, 88)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <!--90's 88-100 -->
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle">90s</h2>
              <p class="chapterText">Les grosses productions dominent le cinéma des années 90. Le numérique s'affirme de plus en plus pour offrir des séquences spectaculaires. En parallèle un cinéma qui joue avec les codes se développe. <em>Pulp Fiction</em> en est le plus bel exemple.</p>
            </div>
          </div>
          <div class="board__slide clickable" v-for="(film, index) in films.slice(88, 100)" @click="moreInfoDown($event)" :style="{ 'background-image': 'url(' + film.image + ')' }">
            <div class="gradientBackgroundFilter"></div>
              <span class="yearOut">{{film.year}}</span>
              <span class="rankAFI">rang : {{film.rank}}</span>
              <div class="filmTitleAuthorsBlock">
                <h2 class="filmTitle">{{film.title}}</h2>
                <span class="filmDirectorIntro">réalisé par<br/></span>
                <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                <span class="filmStudioIntro">studio<br/></span>
                <span class="filmStudio">{{film.studio}}</span>
              </div>
              <div class="moreInfo" style="top: -100vh;">
                  <span class="yearOut">{{film.year}}</span>
                  <span class="rankAFI">Rang : {{film.rank}}</span>
                  <div class="filmSynopsisBlock">
                      <h3 class="filmSynopsisTitle">Synopsis</h3>
                      <p class="filmSynopsis">{{film.synopsis}}</p>
                      <span class="knowMoreButton"><a :href="film.link" target="blank">En savoir plus</a><br/></span>
                      <span class="returnButton" @click="moreInfoUp($event)">Retour</span>
                  </div>
                  <div class="filmTitleAuthorsBlock">
                      <h2 class="filmTitle">{{film.title}}</h2>
                      <span class="filmDirectorIntro">réalisé par<br/></span>
                      <span v-for="director in film.director" class="filmDirector">{{director}}<br/></span>
                      <span class="filmStudioIntro">studio<br/></span>
                      <span class="filmStudio">{{film.studio}}<br/></span>
                  </div>
              </div>
          </div>
          <div class="board__slide">
            <div class="vertically-centered">
              <h2 class="chapterTitle text_centered">FIN</h2>
            </div>
          </div>
      </div>
      <ul class="menu desktopmenu">
        <li @click="slideTo(0)">AFI</li>
        <li @click="slideTo(-slideWidth*7-15)">20s</li>
        <li @click="slideTo(-slideWidth*(4+2+6)-15)">30s</li>
        <li @click="slideTo(-slideWidth*(16+2+6)-15)">40s</li>
        <li @click="slideTo(-slideWidth*(27+3+6)-15)">50s</li>
        <li @click="slideTo(-slideWidth*(43+4+6)-15)">60s</li>
        <li @click="slideTo(-slideWidth*(60+5+6)-15)">70s</li>
        <li @click="slideTo(-slideWidth*(80+6+6)-15)">80s</li>
        <li @click="slideTo(-slideWidth*(88+7+6)-15)">90s</li>
        <li @click="slideTo(1)">FIN</li>
      </ul>
      <ul class="menu simplemenu">
        <li @click="toggleMenu()">MENU</li>
      </ul>
      <ul class="mobilemenu" style="top: 100%">
        <div class="vertically-centered">
          <li @click="slideTo(0)">AFI</li>
          <li @click="slideTo(-slideWidth*7-15)">20s</li>
          <li @click="slideTo(-slideWidth*(4+2+6)-15)">30s</li>
          <li @click="slideTo(-slideWidth*(16+2+6)-15)">40s</li>
          <li @click="slideTo(-slideWidth*(27+3+6)-15)">50s</li>
          <li @click="slideTo(-slideWidth*(43+4+6)-15)">60s</li>
          <li @click="slideTo(-slideWidth*(60+5+6)-15)">70s</li>
          <li @click="slideTo(-slideWidth*(80+6+6)-15)">80s</li>
          <li @click="slideTo(-slideWidth*(88+7+6)-15)">90s</li>
          <li @click="slideTo(1)">FIN</li>
        </div>
        <li @click="toggleMenu()" class="closemenu">FERMER</li>
      </ul>
      <div id="progressBar">
        <div id="progression"></div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      films: [],
      loading: true,
      direction: false,
      slideWidth: 0,
      left: 0,
      menu: false,
      startX: 0
    }
  },
  methods: {
    moreInfoDown (event) {
      var elt = event.currentTarget.lastChild
      event.currentTarget.lastChild.style.top = 0 + 'vh'

      setTimeout(function () {
        elt.children[0].style.opacity = 1
        elt.children[1].style.opacity = 1
      }, 100)

      setTimeout(function () {
        elt.children[2].children[0].style.opacity = 1
        elt.children[2].children[1].style.opacity = 1
      }, 200)

      setTimeout(function () {
        elt.children[2].children[2].style.opacity = 1
        elt.children[2].children[3].style.opacity = 1
      }, 300)

      if (elt.children[3].childElementCount > 5) {
        setTimeout(function () {
          elt.children[3].children[0].style.opacity = 1
          elt.children[3].children[1].style.opacity = 1
          elt.children[3].children[2].style.opacity = 1
        }, 400)

        setTimeout(function () {
          elt.children[3].children[3].style.opacity = 1
          elt.children[3].children[4].style.opacity = 1
          elt.children[3].children[5].style.opacity = 1
        }, 500)
      } else if (elt.children[3].childElementCount > 4) {
        setTimeout(function () {
          elt.children[3].children[0].style.opacity = 1
          elt.children[3].children[1].style.opacity = 1
          elt.children[3].children[2].style.opacity = 1
        }, 400)

        setTimeout(function () {
          elt.children[3].children[3].style.opacity = 1
          elt.children[3].children[4].style.opacity = 1
        }, 500)
      } else {
        setTimeout(function () {
          elt.children[3].children[0].style.opacity = 1
          elt.children[3].children[1].style.opacity = 1
        }, 400)

        setTimeout(function () {
          elt.children[3].children[2].style.opacity = 1
          elt.children[3].children[3].style.opacity = 1
        }, 500)
      }
    },
    moreInfoUp (event) {
      event.stopPropagation()
      var elt = event.currentTarget.parentElement.parentElement
      elt.style.top = -100 + 'vh'

      elt.children[0].style.opacity = 0
      elt.children[1].style.opacity = 0

      elt.children[2].children[0].style.opacity = 0
      elt.children[2].children[1].style.opacity = 0
      elt.children[2].children[2].style.opacity = 0
      elt.children[2].children[3].style.opacity = 0

      if (elt.children[3].childElementCount > 5) {
        elt.children[3].children[0].style.opacity = 0
        elt.children[3].children[1].style.opacity = 0
        elt.children[3].children[2].style.opacity = 0
        elt.children[3].children[3].style.opacity = 0
        elt.children[3].children[4].style.opacity = 0
        elt.children[3].children[5].style.opacity = 0
      } else if (elt.children[3].childElementCount > 4) {
        elt.children[3].children[0].style.opacity = 0
        elt.children[3].children[1].style.opacity = 0
        elt.children[3].children[2].style.opacity = 0
        elt.children[3].children[3].style.opacity = 0
        elt.children[3].children[4].style.opacity = 0
      } else {
        elt.children[3].children[0].style.opacity = 0
        elt.children[3].children[1].style.opacity = 0
        elt.children[3].children[2].style.opacity = 0
        elt.children[3].children[3].style.opacity = 0
      }
    },
    slideTo (value) {
      var element = document.getElementById('board')

      if (value === 1) {
        value = -(element.offsetWidth - window.innerWidth)
      }
      element.style.left = value + 'px'
      this.left = value
      this.handleMenuActive()
      this.handleProgressBar()

      if (this.menu) {
        this.toggleMenu()
      }
    },
    detectScrollDirection (e) {
      var delta = null

      if (!e) {
        e = window.event
      }
      if (!e) {
        e = window.event
      }

      if (e.wheelDelta) {
        delta = e.wheelDelta / 60
      } else if (e.detail) {
        delta = -e.detail / 2
      }

      if (delta !== null) {
        this.direction = delta > 0 ? 'up' : 'down'
      }

      this.handleMouseWheelDirection()
    },
    handleMouseWheelDirection () {
      var element = document.getElementById('board')

      if (this.direction === 'down') {
        this.setLeftValue()
        element.style.left = this.left + 'px'
      } else if (this.direction === 'up') {
        this.setLeftValue()
        element.style.left = this.left + 'px'
      } else {
        console.log('Erreur : Direction du scroll non détécté !')
      }
      this.handleMenuActive()
      this.handleProgressBar()
    },
    setLeftValue () {
      if (this.direction === 'down') {
        if (this.left - 100 < -(document.getElementById('board').offsetWidth - window.innerWidth)) {
          this.left = this.left
        } else if (this.left <= 0) {
          this.left -= 100
        }
      } else if (this.direction === 'up') {
        if (this.left < 0) {
          this.left += 100
        } else {
          this.left = 0
        }
      } else {
        console.log('Erreur : Direction du scroll non détécté !')
      }
    },
    handleProgressBar () {
      var element = document.getElementById('progression')
      var currentPosition = -this.left
      var screenWidth = window.innerWidth
      var boardWidth = document.getElementById('board').offsetWidth - 100
      element.style.width = 100 * currentPosition / (boardWidth - screenWidth) + '%'
    },
    handleMenuActive () {
      if (this.left > -this.slideWidth * 7 - 15) {
        document.getElementsByClassName('menu')[0].children[0].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[0].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (4 + 2 + 6) - 15 && this.left <= -this.slideWidth * 7 - 15) {
        document.getElementsByClassName('menu')[0].children[1].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[1].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (16 + 2 + 6) - 15 && this.left <= -this.slideWidth * (4 + 2 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[2].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[2].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (27 + 3 + 6) - 15 && this.left <= -this.slideWidth * (16 + 2 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[3].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[3].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (43 + 4 + 6) - 15 && this.left <= -this.slideWidth * (27 + 3 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[4].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[4].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (60 + 5 + 6) - 15 && this.left <= -this.slideWidth * (43 + 4 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[5].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[5].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (80 + 6 + 6) - 15 && this.left <= -this.slideWidth * (60 + 5 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[6].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[6].classList.remove('active')
      }

      if (this.left > -this.slideWidth * (88 + 7 + 6) - 15 && this.left <= -this.slideWidth * (80 + 6 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[7].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[7].classList.remove('active')
      }

      if (this.left > -(document.getElementById('board').offsetWidth - window.innerWidth) && this.left <= -this.slideWidth * (88 + 7 + 6) - 15) {
        document.getElementsByClassName('menu')[0].children[8].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[8].classList.remove('active')
      }

      if (this.left <= -(document.getElementById('board').offsetWidth - window.innerWidth)) {
        document.getElementsByClassName('menu')[0].children[9].classList.add('active')
      } else {
        document.getElementsByClassName('menu')[0].children[9].classList.remove('active')
      }
    },
    toggleMenu () {
      if (this.menu) {
        this.menu = false
        document.getElementsByClassName('mobilemenu')[0].style.top = '100%'
      } else {
        this.menu = true
        document.getElementsByClassName('mobilemenu')[0].style.top = '0%'
      }
    },
    handleMoveStart (e) {
      this.startX = e.changedTouches[0].pageX
    },
    handleMoveEnd (e) {
      var element = document.getElementById('board')
      var dist = e.changedTouches[0].pageX - this.startX

      if (dist < 0) {
        if (this.left + dist * 2 < -(document.getElementById('board').offsetWidth - window.innerWidth)) {
          this.left = -(document.getElementById('board').offsetWidth - window.innerWidth)
        } else if (this.left <= 0) {
          this.left += dist * 2
        }
      } else if (dist > 0) {
        if (this.left + dist * 2 < 0) {
          this.left += dist * 2
        } else {
          this.left = 0
        }
      }
      element.style.left = this.left + 'px'
      this.handleProgressBar()
    },
    handleKeyboard (e) {
      var element = document.getElementById('board')

      switch (e.key) {
        case 'ArrowUp':
        case 'ArrowLeft':
          this.direction = 'up'
          this.setLeftValue()
          element.style.left = this.left + 'px'
          break
        case 'ArrowDown':
        case 'ArrowRight':
          this.direction = 'down'
          this.setLeftValue()
          element.style.left = this.left + 'px'
          break
      }

      this.handleMenuActive()
      this.handleProgressBar()
    },
    preloadImage (url) {
      var img = new Image()
      img.src = url
    },
    handleResize () {
      this.slideWidth = document.getElementsByClassName('board__slide')[0].offsetWidth
    }
  },
  created () {
    document.addEventListener('DOMMouseScroll', this.detectScrollDirection)
    document.addEventListener('mousewheel', this.detectScrollDirection)
    document.addEventListener('touchstart', this.handleMoveStart, false)
    document.addEventListener('touchend', this.handleMoveEnd, false)
    window.addEventListener('keydown', this.handleKeyboard, false)
    window.addEventListener('resize', this.handleResize, false)

    var url
    if (window.innerWidth < 500) {
      url = 'static/films.json'
    } else {
      url = 'static/films.json'
    }

    this.$http.get(url).then((response) => {
      this.films = response.data
      for (var i = 0; i < this.films.length; i++) {
        this.preloadImage(this.films[i].image)
      }
    }, (response) => {
      console.log('erreur', response)
    }).then(loading => {
      setTimeout(function () {
        this.loading = false
      }.bind(this), 2000)
    })
  },
  mounted () {
    this.slideWidth = document.getElementsByClassName('board__slide')[0].offsetWidth
    this.handleMenuActive()
    this.handleProgressBar()
  },
  destroyed () {
    document.removeEventListener('DOMMouseScroll', this.detectScrollDirection)
    document.removeEventListener('mousewheel', this.detectScrollDirection)
    document.removeEventListener('touchstart', this.handleMoveStart, false)
    document.removeEventListener('touchend', this.handleMoveEnd, false)
    window.removeEventListener('keydown', this.handleKeyboard, false)
    window.addEventListener('resize', this.handleResize, false)
  }
}
</script>

<style>
  @font-face {
    font-family: Futura-Normal;
    src: url('/static/fonts/futura-pt-medium.otf');
  }

  .chapterTitle,
  .yearOut,
  .rankAFI,
  .filmTitle,
  .originalFilmTitle,
  .filmSynopsisTitle,
  .filmDirector,
  .filmStudio { font-family: 'Futura-Normal', monospace; }

  .chapterText,
  .originalFilmTitle,
  .knowMoreButton,
  .returnButton,
  .filmSynopsis,
  .filmDirectorIntro,
  .filmStudioIntro,
  .menu,
  .mobilemenu { font-family: 'Futura-Normal', serif; }

  body { margin: 0; }

  .vertically-centered {
    margin-top: 50vh;
    transform: translateY(-50%);
  }

  .clickable { cursor: pointer; }

  .text_centered { text-align: center; }

  .chapterTitle.text_centered { padding-left: 0; }

  #app{
    position: fixed;
    width: 100vw;
    height: 100vh;
  }

  #board{
    position: relative;
    display: table;
    width: inherit;
    height: 100%;
    transition: left 1s cubic-bezier(.39,.575,.565,1)
  }

  #preloader{
    position: absolute;
    width: inherit;
    height: inherit;
    background-color: #313131;
    z-index: 100000;
  }

  #preloader img{
    width: auto;
    height: auto;
    margin-top: 100vh;
    margin-left: 50vw;
    transform: translate(-50%, -50%);
    border: none;
  }

  @media screen and (max-width: 500px) {
    #preloader img {
      width: auto;
      margin-left: 100vw;
    }
  }

  .board__chapter{
    position: inherit;
    display: table-cell;
    min-width: calc(100vw - 600px);
    height: inherit;
  }

  .board__chapter h1{
    position: fixed;
    z-index: 1;
    top: 10px;
    left: 10px;
  }


  .chapterTitle,
  .chapterText {
    width: inherit;
    color: #fff;
  }

  .chapterTitle {
    margin: 0;
    font-size: 72px;
    padding-left: 100px;
    position: relative;
  }

  @media screen and (max-width: 500px) {
    .chapterTitle {
      font-size: 40px;
      padding-left: 50px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .chapterTitle {
      font-size: 40px;
      padding-left: 50px;
    }
  }

   .chapterText {
     font-size: 20px;
     margin: 0;
     padding: 20px 100px 0 100px;
    }

    @media screen and (max-width: 500px) {
      .chapterText {
        font-size: 14px;
        padding: 20px 50px 0 50px;
      }
    }

    @media screen and (max-width: 800px) and (max-height: 500px) {
      .chapterText {
        font-size: 14px;
        padding: 20px 50px 0 50px;
      }
    }

  .board__slide{
    position: relative;
    z-index: 10;
    display: table-cell;
    min-width: 610px;
    max-width: inherit;
    height: inherit;
    overflow: hidden;
    background-color: #000;
    background-size: cover;
    background-position: center;
    filter: sepia(50%);
    transition: all 1s ease-in
  }

  .board__slide:hover {
    filter: none;
  }

  @media screen and (max-width: 500px) {
    .board__slide{ min-width: 320px; }
  }

  .board__slide > div > .chapterTitle,
  .board__slide > .chapterTitle,
  .board__slide > .yearOut,
  .board__slide > .rankAFI,
  .board__slide > .filmTitleAuthorsBlock > .filmTitle,
  .board__slide > .filmTitleAuthorsBlock > .filmDirector,
  .board__slide > .filmTitleAuthorsBlock > .filmStudio {
    color: #a17f1a
  }

  .board__slide:hover > div > .chapterTitle,
  .board__slide:hover > .chapterTitle,
  .board__slide:hover > .yearOut,
  .board__slide:hover > .rankAFI,
  .board__slide:hover > .filmTitleAuthorsBlock > .filmTitle,
  .board__slide:hover > .filmTitleAuthorsBlock > .filmDirector,
  .board__slide:hover > .filmTitleAuthorsBlock > .filmStudio {
    color: #996515;
    transition: color 1s cubic-bezier(.39,.575,.565,1)
  }

  .gradientBackgroundFilter {
    position: absolute;
    top: 0;
    height: 100%;
    width: 100%;
    background: -moz-linear-gradient(top, rgba(0,0,0,1) 0%, rgba(0,0,0,0) 50%, rgba(0,0,0,1) 100%); /* FF3.6-15 */
    background: -webkit-linear-gradient(top, rgba(0,0,0,1) 0%,rgba(0,0,0,0) 50%,rgba(0,0,0,1) 100%); /* Chrome10-25,Safari5.1-6 */
    background: linear-gradient(to bottom, rgba(0,0,0,1) 0%,rgba(0,0,0,0) 50%,rgba(0,0,0,1) 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#000000', endColorstr='#000000',GradientType=0 ); /* IE6-9 */
  }

  .yearOut,
  .rankAFI,
  .filmTitleBlock,
  .filmTitleAuthorsBlock {
    position: absolute;
    z-index: 100;
  }

  .filmTitle,
  .originalFilmTitle,
  .filmSynopsisTitle,
  .filmTitleAuthorsBlock {
    width: 100%;
    text-align: center;
  }

  .yearOut {
    top: 10px;
    left: 25px;
    font-size: 72px;
    text-shadow: 2px 2px #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .yearOut {
      font-size: 50px;
    }
  }

  @media screen and (max-width: 500px) {
    .yearOut {
      font-size: 36px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .yearOut {
      font-size: 24px;
    }
  }

  .rankAFI {
    top: 30px;
    right: 25px;
    font-size: 24px;
    text-transform: capitalize;
    text-shadow: 1px 1px #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .rankAFI {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 500px) {
    .rankAFI {
      top: 15px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .rankAFI {
      top: 10px;
      font-size: 24px;
    }
  }

  .filmTitleBlock {
    width: calc(100% - 70px);
    top: 80px;
    left: calc(50% - (100% - 70px)/2);
  }

  @media screen and (max-width: 500px) {
    .filmTitleBlock {
      width: calc(100% - 10px);
      top: 35px;
      left: calc(50% - (100% - 10px)/2);
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmTitleBlock {
      width: calc(100% - 10px);
      top: 20px;
      left: calc(50% - (100% - 10px)/2);
    }
  }

  .filmTitle {
    font-size: 46px;
    margin-bottom: 10px;
    text-transform: uppercase;
    text-shadow: 2px 2px #fff;
    margin: 0;
    width: 90%;
    padding-left: 5%;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmTitle {
      font-size: 38px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmTitle {
      font-size: 28px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmTitle {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmTitle {
      font-size: 20px;
    }
  }

  .originalFilmTitle {
    font-size: 18px;
    font-style: italic;
    color: #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .originalFilmTitle {
      font-size: 12px;
    }
  }

  @media screen and (max-width: 500px) {
    .originalFilmTitle {
      font-size: 12px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .originalFilmTitle {
      margin: 0 5px;
      font-size: 12px;
    }
  }

  .filmTitleAuthorsBlock {
    width: 100%;
    bottom: 1080px;
  }

  .filmDirectorIntro {
    font-size: 18px;
    font-style: italic;
    font-weight: bold;
    color: #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmDirectorIntro {
      font-size: 12px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmDirectorIntro {
      font-size: 10px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmDirectorIntro {
      font-size: 10px;
    }
  }

  .filmDirector {
    font-size: 36px;
    text-transform: uppercase;
    text-shadow: 0.03em 0.03em #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmDirector {
      font-size: 30px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmDirector {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmDirector {
      font-size: 18px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmDirector {
      font-size: 12px;
    }
  }

  .filmStudioIntro {
    font-size: 18px;
    font-style: italic;
    font-weight: bold;
    color: #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmStudioIntro {
      font-size: 12px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmStudioIntro {
      font-size: 10px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmStudioIntro {
      font-size: 10px;
    }
  }

  .filmStudio {
    font-size: 24px;
    text-transform: uppercase;
    text-shadow: 0.03em 0.03em #fff;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmStudio {
      font-size: 18px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmStudio {
      font-size: 14px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmStudio {
      font-size: 18px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmStudio {
      font-size: 12px;
    }
  }

  .filmTitleAuthorsBlock{ bottom: 70px; }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmTitleAuthorsBlock{ bottom: 58px; }
    .moreInfo > .filmTitleAuthorsBlock{ bottom: 50px; }
  }

  @media screen and (max-width: 500px) {
    .filmTitleAuthorsBlock{ bottom: 50px; }
    .moreInfo > .filmTitleAuthorsBlock{ bottom:50px; }
  }

  @media screen and (max-width: 600px) and (max-height: 500px) {
    .filmTitleAuthorsBlock{ bottom: 165px; }
    .moreInfo > .filmTitleAuthorsBlock{ bottom: 35px; }
  }

  @media screen and (max-width: 800px) and (max-height: 350px) {
    .filmTitleAuthorsBlock{ bottom: 40px; }
    .moreInfo > .filmTitleAuthorsBlock{ bottom: 40px; }
  }

  .moreInfo > .yearOut,
  .moreInfo > .rankAFI,
  .moreInfo > .filmTitleAuthorsBlock > .filmTitle,
  .moreInfo > .filmTitleAuthorsBlock > .originalFilmTitle,
  .moreInfo > .filmSynopsisBlock > .filmSynopsisTitle,
  .moreInfo > .filmSynopsisBlock > .filmSynopsis,
  .moreInfo > .filmSynopsisBlock > .knowMoreButton,
  .moreInfo > .filmSynopsisBlock > .returnButton,
  .moreInfo > .filmTitleAuthorsBlock > .filmDirectorIntro,
  .moreInfo > .filmTitleAuthorsBlock > .filmDirector,
  .moreInfo > .filmTitleAuthorsBlock > .filmStudioIntro,
  .moreInfo > .filmTitleAuthorsBlock > .filmStudio {
    text-shadow: 0.03em 0.03em #996515;
    opacity: 0;
    transition: opacity 1s cubic-bezier(.39,.575,.565,1);
  }

  .filmSynopsisBlock {
    margin-top: 25vh;
  }

  img {
    position: absolute;
    top: -50vh;
    height: 100vh;
    width: 100%;
    border: 5px solid #000;
    border-bottom: 50px;
    transform: translateY(50vh);
  }

  @media screen and (max-width: 500px) {
    img {
      top: -50vh;
      left: -50vw;
      height: 100vh;
      width: auto;
      transform: translate(50vw, 50vh);
    }
  }

  .moreInfo {
    position: absolute;
    z-index: 100;
    min-width: inherit;
    height: 100vh;
    background-color: rgba(0,0,0,.9);
    transition: top .5s cubic-bezier(.39,.575,.565,1);
    color: #fff;
    cursor: default;
  }

  .filmSynopsisTitle {
    font-size: 36px;
    top: 260px;
    margin: 5px 0;
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmSynopsisTitle {
      font-size: 30px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmSynopsisTitle {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmSynopsisTitle {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmSynopsisTitle {
      font-size: 18px;
    }
  }

  .filmSynopsis {
    top: 350px;
    padding: 0 50px;
    font-size: 16px;
  }

  @media screen and (max-width: 1400px) and (min-height: 768px) {
    .filmSynopsis {
      padding: 0 20px;
      font-size: 14px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 768px) {
    .filmSynopsis {
      font-size: 14px;
    }
  }

  @media screen and (max-width: 1280px) and (min-height: 500px) {
    .filmSynopsis {
      padding: 0 20px;
      font-size: 14px;
    }
  }

  @media screen and (max-width: 500px) {
    .filmSynopsis {
      padding: 0 10px;
      font-size: 14px;
    }

    .filmSynopsisBlock {
      margin-top: 70px;
    }
  }

  @media screen and (max-width: 800px) and (max-height: 500px) {
    .filmSynopsis {
      padding: 0 10px;
      margin: 10px 0 0 0;
      font-size: 14px;
    }
  }

  .knowMoreButton,
  .returnButton {
    font-size: 18px;
    cursor: pointer;
   }

   @media screen and (max-width: 500px) {
     .knowMoreButton,
     .returnButton {
       font-size: 14px;
      }
   }

   @media screen and (max-width: 800px) and (max-height: 500px) {
     .knowMoreButton,
     .returnButton {
       font-size: 14px;
      }
   }

   .knowMoreButton a { color: #fff; }

   .knowMoreButton:hover a,
   .returnButton:hover {
     color: silver;
     transition: color .5s cubic-bezier(.39,.575,.565,1);
   }

  .knowMoreButton {
    margin-left: calc(50% - 50px);
    text-decoration: none;
  }

  @media screen and (max-width: 500px) {
    .knowMoreButton {
      margin-left: calc(50% - 39px);
     }
  }

  .returnButton { margin-left: calc(50% - 24px); }

  @media screen and (max-width: 500px) {
    .returnButton { margin-left: calc(50% - 19px); }
  }

  ul.menu {
    position: fixed;
    bottom: -24px;
    left: -40px;
    z-index: 500;
    height: 40px;
    width: 100vw;
    background-color: #000;
  }

  ul.mobilemenu {
    position: fixed;
    bottom: -24px;
    left: -40px;
    z-index: 500;
    height: 100vh;
    width: 100vw;
    background-color: #000;
    font-size: 20px;
    color: #fff;
    text-align: center;
    list-style-type: none;

  }

  ul.menu > li {
    float: left;
    list-style-type: none;
    height: 20px;
    width: 10%;
    background-color: black;
    color: #000;
    font-size: 18px;
    text-align: center;
    text-shadow: 1px 1px #fff;
    cursor: pointer;
    transition: color .5s cubic-bezier(.39,.575,.565,1);
  }

  .mobilemenu > li.closemenu:hover,
  ul.mobilemenu > div > li:hover,
  ul.menu > li.active,
  ul.menu > li:hover {
    color: #996515;
  }

  .mobilemenu > li.closemenu,
  ul.mobilemenu > div > li {
    transition: color .5s cubic-bezier(.39,.575,.565,1);
    cursor: pointer;
  }

  .mobilemenu {
    margin: 0;
    transition: top .5s cubic-bezier(.39,.575,.565,1);
  }

  .mobilemenu > div > li { padding: 3px; }

  .mobilemenu > li.closemenu {
    position: absolute;
    bottom: 10px;
    left: 40px;
    font-size: 18px;
  }

  .simplemenu { display: none; }

  @media screen and (max-width: 670px) {
    .simplemenu { display: inline; }
    .desktopmenu { display: none; }
  }

  #progressBar{
    position: fixed;
    bottom: 0;
    z-index: 1000;
    width: 100%;
    height: 8px;
    background-color: #696969;
  }

  #progression{
    height: inherit;
    background-color: #fff;
    transition: width 1s cubic-bezier(.39,.575,.565,1)
  }

</style>
