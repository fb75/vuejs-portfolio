<template>
  <v-app>
    <main>
      <v-content>
        <v-container grid-list-lg>
          <v-layout row wrap>            
              <router-view style="margin-left:0;"></router-view>
              <v-spacer></v-spacer>                        
            <!-- <component :is="component"></component> -->                
            <app-content></app-content>          
          </v-layout>
        </v-container>
      </v-content>
    </main>
    <v-footer class="blue darken-3">
      <v-layout row wrap align-center>
        <v-flex xs12>
          <div class="white--text ml-3">
            <small>Made with Vue.js and Vuetify.js with</small>
            <v-icon class="red--text">favorite</v-icon>
              <img style="width:30px; height: 30px; float:right;" :src="linux"></img>
            
          </div>

        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
  import Know from './components/Know.vue';
  import Content from './components/Content.vue';
  import Dialog from './components/Dialog.vue';  
  import Section from './components/Section.vue';      
  import Portfolio from './components/Portfolio.vue';      
  export default {   
    components: {
      appKnow: Know,
      appContent: Content,
      appDialog: Dialog,
      appSection: Section,
      appPortfolio: Portfolio,
    },
    data () {
      return {  
      linux: './static/linux-logo.png'       
      }
    }
  }

</script>

<style scoped>
  .content {
/*background: linear-gradient(-50deg, #1F1C2C, #928DAB);
background-size: 400% 400%;
animation: movingGradient 8s ease-in-out infinite;  */
/*background: #BBD2C5;/*  /* fallback for old browsers */
background: -webkit-linear-gradient(349deg, #667db6,#0082c8, #fff);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(349deg, #667db6,#0082c8, #fff); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

background-size: 100% 100%;
animation: movingGradient 3s ease-in-out infinite;  
}

@keyframes movingGradient {
  0% {background-position:49% 40%}
  50% {background-position:52% 100%}
  100% {background-position:49% 40%}
}  

</style>