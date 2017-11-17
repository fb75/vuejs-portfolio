<template>
  <v-layout column style="background:#292E49; width:100%; margin-left:0;" class="white--text">
    <v-flex xs12 md12 class="ml-1 mr-1">
       <v-container fluid grid-list-md>
        <v-layout row wrap>
          <v-flex
            v-bind="{ [`xs${card.flex}`]: false }"
            v-for="card in cards"
            :key="card.title"
          >
          <v-card class="elevation-1" style="font-size: 1.3em;"> 
            <div class="blue--text text--darken3 pl-2 pr-2 text-xs-center">{{card.description}}</div>
              <v-card-media
                :src="card.src"
                height="200px"
                contain
                >
                <v-container fill-height fluid>
                  <v-layout fill-height>
                    <v-flex xs12 align-end flexbox>                                            
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card-media>
              <v-card-actions class="">                
                <v-spacer></v-spacer>
                <a :href="link" v-if="card.title === 'Matteo Valentini Fotografia'"><v-icon color="blue darken--4">fa-share</v-icon></a>
                <v-btn icon @click="" v-if="card.title === 'API REST'">                 
                  <app-dialogfs v-if="card.title === 'API REST'"></app-dialogfs>
                </v-btn>                  
              </v-card-actions>              
            </v-card>          
          </v-flex>
        </v-layout>
       </v-container>
    </v-flex>    
  </v-layout>

</template>

<script>
  import Dialogfs from './Dialogfs.vue';
  export default {
    data: () => ({
      dialog: false,
      link: 'http://www.matteovalentini.com',      
      cards: [
        { title: 'Matteo Valentini Fotografia', src: '../static/matteovalentini.png', flex: 6,
        description: 'Sito web realizzato con CMS Wordpress | Stile: minimal - bianco e nero'
        },
        { title: 'API REST', src: '../static/apicloud.png', flex: 6,
        description: 'Esempio di chiamata ad API REST per la visualizzazione degli ultimi dieci articoli dal sito Washington Post'         }
      ]
    }),
    components: {
      appDialogfs: Dialogfs
    }        
  }  
</script>

<style>
  .imgcont {
    background: contain; 
  }
</style>