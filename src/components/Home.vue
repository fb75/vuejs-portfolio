<template> 
<v-flex xs12 md4 offset-xs1 class="pr-1 pl-1 low blue--text text--darken-4">
  <div class="text-xs-center pt-4 pb-4">
    <v-avatar size="125px">
    <!-- <transition name="cool"
    mode="in-out"
    @after-enter="afterEnter"
    appear> -->
      <img                
        :src="link"       
        class="elevated-7" 
      >
    <!-- </transition> -->
    </v-avatar>
    <h4>Francesco <span style="font-weight:bold">Brachini</span></h4>
    <v-divider style="width:200px; margin: auto;"></v-divider>
    <h5 class="text-xs-center" 
      style="font-style: italic;
      font-family: 'roboto';
      padding: 2%;
      color: #BBD2C5;
      ">
      <div class="cont" style="opacity: 1;">
        <div class="j" style="position: relative; display: inline-block; opacity: 0;">J</div>
        <div class="u" style=" position: relative; display: inline-block; opacity: 0;">u</div>
        <div class="n" style="position: relative; display: inline-block; opacity: 0;">n</div>
        <div class="i" style="position: relative; display: inline-block; opacity: 0;">i</div>
        <div class="o" style="position: relative; display: inline-block; opacity: 0;">o</div>
        <div class="r" style="position: relative; display: inline-block; opacity: 0;">r</div>
        <div class="space" style="position: relative; display: inline-block; opacity: 0;"> </div>
        <div class="f" style="position: relative; display: inline-block; opacity: 0;">F</div>
        <div class="rr" style="position: relative; display: inline-block; opacity: 0;">r</div>
        <div class="oo" style="position: relative; display: inline-block; opacity: 0;">o</div>
        <div class="nn" style="position: relative; display: inline-block; opacity: 0;">n</div>
        <div class="t" style="position: relative; display: inline-block; opacity: 0;">t</div>
        <div class="e" style="position: relative; display: inline-block; opacity: 0;">e</div>
        <div class="nnn" style="position: relative; display: inline-block; opacity: 0;">n</div>
        <div class="d" style="position: relative; display: inline-block; opacity: 0;">d</div><br>
        <!-- <div class="space2" style="position: relative; display: inline-block; opacity: 0;"> </div> -->
        <div class="dd" style="position: relative; display: inline-block; opacity: 0;">D</div>
        <div class="ee" style="position: relative; display: inline-block; opacity: 0;">e</div>
        <div class="v" style="position: relative; display: inline-block; opacity: 0;">v</div>
        <div class="eee" style="position: relative; display: inline-block; opacity: 0;">e</div>
        <div class="l" style="position: relative; display: inline-block; opacity: 0;">l</div>
        <div class="ooo" style="position: relative; display: inline-block; opacity: 0;">o</div>
        <div class="p" style="position: relative; display: inline-block; opacity: 0;">p</div>
        <div class="eeee" style="position: relative; display: inline-block; opacity: 0;">e</div>
        <div class="rrr" style="position: relative; display: inline-block; opacity: 0;">r</div>
      </div>
    </h5>
    <v-layout row justify-space-around class="pt-1">
      <v-flex xs12>
        <ul class="ic">
          <li><a :href="social.faLink"><v-icon style="color:#BBD2C5;">fa-facebook</v-icon></a>    
            </li>
          <li><a :href="social.instaLink"><v-icon style="color:#BBD2C5;">fa-instagram</v-icon></a></li>
          <li><a :href="social.githLink"><v-icon style="color:#BBD2C5;">fa-github</v-icon></a></li>
          <li><a :href="social.linkLink"><v-icon style="color:#BBD2C5;">fa-linkedin</v-icon></a></li>
        </ul>
      </v-flex>      
    </v-layout>
  </div>
  <v-list two-line style="background-color:#dbe1ff">
      <v-list-tile @click="">
        <v-list-tile-action>
          <v-icon color="blue">fa-phone</v-icon>
        </v-list-tile-action>
        <v-list-tile-content class="blue--text text--darken-4">
          <v-list-tile-title>+39 393 7278 710</v-list-tile-title>
          <v-list-tile-sub-title class="blue--text text--darken-1">Mobile</v-list-tile-sub-title>
        </v-list-tile-content>
<!--         <v-list-tile-action>
          <v-icon>chat</v-icon>
        </v-list-tile-action> -->
      </v-list-tile>
      <v-divider inset></v-divider>
      <v-list-tile @click.stop="">
        <v-list-tile-action>
          <v-icon color="blue" medium>fa-envelope</v-icon>
        </v-list-tile-action>
        <v-list-tile-content class="blue--text text--darken-4">
          <a href="mailto:gunner19751@gmail.com"><v-list-tile-title class="blue--text text--darken-4">{{mail}}</v-list-tile-title></a>
          <v-list-tile-sub-title class="blue--text text--darken-1">Email</v-list-tile-sub-title>
        </v-list-tile-content>
      </v-list-tile>
    <v-divider inset></v-divider>
      <v-list-tile @click="showMap = !showMap">
        <v-list-tile-action>
          <v-icon color="blue">fa-map-marker</v-icon>
        </v-list-tile-action>
        <v-list-tile-content class="blue--text text--darken-4">
          <v-list-tile-title>Via P. Acquacotta, 7</v-list-tile-title>
          <v-list-tile-sub-title class="blue--text text--darken-1">06125 Perugia, IT</v-list-tile-sub-title>           
        </v-list-tile-content>
      </v-list-tile>
<!--           <transition name="slide">
      <app-googlemaps class="mt-1" v-if="showMap"></app-googlemaps>
    </transition> -->
    </v-list>
    <transition name="slide">
      <app-googlemaps class="mt-1" v-if="showMap"></app-googlemaps>
    </transition>
</v-flex>
</template>

<script>
import Googlemaps from './Googlemaps.vue';
export default {  
  data () {
    return {
      mail: 'gunner19751@gmail.com',
      size: '300px',
      class: 'elevated-7',
      link: '../static/img1.jpg',
      showMap: false,
      social: {
      faLink: 'https://facebook.com/francesco.brachini1',
      instaLink: 'https://www.instagram.com/francbrk/',
      githLink: 'https://github.com/fb75',
      linkLink: 'https://www.linkedin.com/in/francesco-brachini-98482a145/'          
      }       
    }
  },
  components: {
    appGooglemaps: Googlemaps,    
  }
}
</script>


<style>

a, u {
  text-decoration: none;
}
.low {
  margin-top: 18px;
}
.animgrad {
/*background: linear-gradient(45deg, #6a69bc,#00fc82);*/
background: #BBD2C5;  /* fallback for old browsers */
background: -webkit-linear-gradient(to right, #292E49, #536976, #BBD2C5);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to right, #292E49, #536976, #BBD2C5); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
background-size: 200% 200%;
animation: movingGradient 8s ease-in-out infinite;  
}
@keyframes movingGradient {
  0% {background-position:49% 40%}
  50% {background-position:52% 100%}
  100% {background-position:49% 40%}
}

#googlemap {  
  width: 100%;
  height: 100%;
  margin: auto;
}

.ic{
  margin:0;
  padding:0;
  display:flex;  
  margin-top: 20px;
}
.ic li {
  list-style: none;
  margin:auto;

}
.ic li a {
  position: relative;
  display: block;
  width: 50px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  background: #292E49;
  border-radius: 50%;    
  transition: .2s ease-out;
}
.ic li a:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  /*background: #ffee10;*/
  background: #536976;
  transition: .2s ease-out;
  transform: scale(.9);
  z-index: -1;
}
.ic li a:hover:before {
  transform: scale(1.1);
  box-shadow: 0 0 15px #dbe1ff;
}
.ic li a:hover {
  color: #ffee10;
  box-shadow: 0 0 5px #dbe1ff;
  text-shadow: 0 0 5px #dbe1ff;
}
.slide-enter {
    opacity: 0;
}
.slide-enter-active {
    animation: slide-in .5s ease-out forwards;
    transition: .5s;
}
.slide-leave {
}
.slide-leave-active {
    animation: slide-out .3s ease-out forwards;
    transition: opacity .5s;
    opacity: 0;
}

@keyframes slide-in {
  0% {
    transform: translateX(-120px);
  }
  25% {
    transform: translateX(0);
  }
  50% {
  transform: translateX(30px);
  }    
  75% {
  transform: translateX(-30px);
  }    
  100% {
  transform: translateX(0);
  }      
}

@keyframes slide-out {
  from {
      transform: translateY(0);
  }
  to {
      transform: translateY(20px);
  }
} 

.cont {
    color: #fff;
    margin: 0;
    letter-spacing: 2px;
}


.j {
display: block;
  animation: b 1s ease-out forwards;
  }

.u {
display: block;
  animation: b 1s ease-out forwards;
  animation-delay: .2s;
  }
.n {
display: block;
  animation: b 1s ease-out forwards;
  animation-delay: .3s;
  }
.i {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .4s;
  }
.o {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .5s;
  }
.r {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .6s;
  }
.space {
display: none;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .7s;
  }
.f {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .8s;
  }
.rr {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: .9s;
  }
.oo {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1s;
  }
.nn {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.1s;
  }
.t {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.2s;
  }
.e {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.3s;
  }
.nnn {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.4s;
  }
.d {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.5s;
  }
.space2 {
display: none;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.6s;
  }
.dd {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.7s;
  }
.ee {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.8s;
  }
.v {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 1.9s;
  }
.eee {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2s;
  }
.l {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2.1s;
  }
.ooo {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2.2s;
  }
.p {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2.3s;
  }
.eeee {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2.4s;
  }
.rrr {
display: block;
  //font-family: 'ubuntu';
  animation: b 1s ease-out forwards;
  animation-delay: 2.5s;
  }

@keyframes b {
  0% {
    transform: translateY(10px) rotateX(180deg);    
  }
  50% {
    transform: translateY(-10px) rotateX(-180deg);    
  }
  /*99%{ transform: scale (2,2); }*/
  100%  
  {
    transform: translateY(0px) rotateX(0);
    opacity: 1;
  }
}

</style>
