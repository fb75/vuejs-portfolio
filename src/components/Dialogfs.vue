<template>
  <v-layout row justify-center>
    <v-dialog v-model="dialog" fullscreen transition="dialog-bottom-transition" :overlay=false>
      <v-btn flat icon slot="activator">
      <v-icon color="blue darken--4">fa-share</v-icon>
      </v-btn>
      <v-card>
        <v-toolbar dark color="primary">
          <v-btn icon @click.native="dialog = false" dark>
            <v-icon>fa-close</v-icon>
          </v-btn>
          <v-toolbar-title>Washington Post</v-toolbar-title>
          <v-spacer></v-spacer>
        </v-toolbar>
        <v-card>
          <v-container grid-list-lg fluid class="blue lighten-4">
            <v-layout justify-space-around row wrap>
              <v-flex
                xs10 md3
                class="mb-2 mt-2 ml-2 mr-2"
                v-for="(article, i) in articles"
                :key="i"> 
                <v-card>
                  <v-card-media                  
                    :src="article.urlToImage"
                    height="250px">
                  </v-card-media>
                  <v-container grid-list-lg text-xs-center fluid>
                    <v-layout fill-height>
                        <v-flex xs12 align-end flexbox>
                        <p class="headline">{{article.title}}</p><br>
                        <span class="mt-1">Autore: </span><span class="grey--text mt-1"><strong>{{article.author}}</strong></span><br>
                        <span class="text-xs-center mt-1"><a :href="article.url">Link all'articolo</a></span><br>
                        <section class="blue--text text--darken-4">{{article.description}}</section>
                        </v-flex>
                      </v-layout>
                    <v-flex xs12>
                  </v-flex>
                </v-container>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-card>
    </v-card>
</v-dialog>
</v-layout>
</template>

<script>
  export default {
    data () {
      return {
        articles: [],
        dialog: false        
    }
   } ,
    mounted() {
      this.hacking();
    },    
    methods: {
      hacking() {
          fetch('https://newsapi.org/v2/top-headlines?sources=the-washington-post&apiKey=3fe769773f5f4c679d640ef5b3706b50')
          .then(response => response.json())
          .then((response) => {                    
              this.articles = response.articles;
              console.log(response);
              console.log(this.articles);
          });
      }  
    }
}  
</script>

<style>
</style>