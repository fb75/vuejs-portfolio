<template>
  <v-layout column fluid style="background:#292E49;">  
          <v-flex xs12 v-for="card in cards" :key="card.title">
          <v-card color="blue lighten-2 white--text" class="white--text">
            <v-container grid-list-lg>
              <v-layout row fluid>
                <v-flex xs12>
                  <div>
                    <div class="headline">{{card.title}}</div>
                    <div>{{card.description}}</div>
                    <v-card> 
                    <!-- JS List Items -->
                      <v-list v-if="card.title === 'JavaScript'" class="blue lighten-2">          
                        <v-icon small @click.stop="clicked()" class="mt-0 mb-3 blue--text text--darken-2">fa-info-circle
                        </v-icon>                        
                        <v-list-tile avatar 
                        class="mt-1" 
                        v-for="jsitem in jsitems" 
                        v-bind:key="jsitem.title"
                        v-if="click">
                        <v-layout row fluid v-if="click">
                          <v-flex xs6 class="mt-1">
                          <v-list-tile-title class="mt-2 text-xs-center">
                            <p style="font-size:13px">{{jsitem.title}}</p>
                            </v-list-tile-title>                          
                          </v-flex>
                          <v-flex xs6>                            
                          <img :src="jsitem.avatar" class="mb-2 ml-3" style="width:50px;height:50px;"></img>
                          </v-flex>
                        </v-layout>
                        </v-list-tile>                    
                      </v-list>
                      <!-- CSS3 list items -->
                      <v-list v-if="card.title === 'CSS3'" class="blue lighten-2">          
                        <v-icon small @click.stop="clicked2()" class="mt-0 mb-3 blue--text text--darken-2">fa-info-circle
                        </v-icon>
                        <v-list-tile avatar 
                        class="mt-1" 
                        v-for="citem in citems" 
                        v-bind:key="citem.title"
                        v-if="click2">
                        <v-layout row fluid v-if="click2">
                          <v-flex xs6 class="mt-1">
                          <v-list-tile-title class="mt-2 text-xs-center">
                            <p style="font-size:13px">{{citem.title}}</p>
                            </v-list-tile-title>                          
                          </v-flex>
                          <v-flex xs6>                            
                          <img :src="citem.avatar" class="mb-2" style="width:50px;height:50px;"></img>
                          </v-flex>
                        </v-layout>
                        </v-list-tile>                    
                      </v-list>
                    </v-list>
                  </v-card>
                  </div>
                </v-flex>
                <v-flex xs5>                
                    <v-card-media
                      :src="card.icon"
                      height="75px"
                      contain
                    ></v-card-media>                    
                </v-flex>
              </v-layout>
            </v-container>
          </v-card>
        </v-flex>

  </v-layout> 
</template>

<script>  
  export default {
    data () {
      return {
        click: false,        
        click2: false,
        cards: [ 
          {
            icon: '../static/html.png', title: 'HTML5', 
            description: 'Hyper Text Markup Language'
          },{
            icon: '../static/css.png', title: 'CSS3', 
            description: 'Cascading Style Sheets'
          }, 
          {
            icon: '../static/javascript.svg', title: 'JavaScript', 
            description: 'ES5 / ES6'
          },
            {
            icon: '../static/wordpress.png', title: 'CMS Open Source', 
            description: 'Wordpress'
          }
        ],
        jsitems: [
          { icon: true, title: 'Npm.js', avatar: '../static/npm-icon.png' },
          { icon: true, title: 'Node.js', avatar: '../static/nodejs.png' },
          { title: 'Express.js', avatar: '/static/express.svg' },
          { icon: true, title: 'WebPack.js', avatar: '../static/webpack.png' },

          { title: 'Vue.js', avatar: '../static/logo.png' },          
          { title: 'Vuetify.js', avatar: '../static/vuetifyjs.png' },
        ],
        citems: [
        {title: 'Sass', avatar: '../static/sass.png'}
      ]
      }
    },
    methods: {
      clicked() {
        this.click = !this.click;                  
      },
      clicked2() {
      this.click2 = !this.click2;                  
      }    
    }        
}
     
    
</script>

<style scoped>
.slide-enter {
    /* We already set up this state with the @keyframe FOR THE ANIMATION!
    transform: translateY(20px);*/

    /*adding and mixing*/
    opacity: 0;
}
.slide-enter-active {
    animation: slide-in .5s ease-out forwards;
    transition: .5s;
}
.slide-leave {
    /* Here we don't set again because is the default position of the element */
}
.slide-leave-active {
    animation: slide-out .3s ease-out forwards;
    /* We have to declare wich transition or animation leads the duration in the markup when both runs togheter */
    transition: opacity .5s;
    opacity: 0;
    /* this to don't let snap up when deleting items */
   /* position: absolute;*/
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

</style>