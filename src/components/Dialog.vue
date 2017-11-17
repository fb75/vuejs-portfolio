<template>
  <v-layout row justify-center>
    <v-btn flat icon color="primary" @click.native.stop="dialog = true">
      <v-icon>fa-info</v-icon>
      </v-btn>
    <v-dialog v-model="dialog">
      <v-card>
        <v-card-title class="pt-1 pb-1 mt-2 mb-2 text-xs-center headline blue--text text--darken-4">
          Corso di Qualifica Professionale Tecnico Specialista in Applicazioni Informatiche per P.M.I. | TUCEP Perugia - 2015          
        </v-card-title>
        <v-flex xs12 class="text-xs-center">
        <img style="width: 20px; height: 15px;" :src="itaflag">
        <img style="width: 20px; height: 15px;" :src="ueflag"> 
      </v-flex>
        <v-card-text>
          <v-divider></v-divider>
          <v-flex xs12 d-flex>
          <ul class="text-xs-left">
          <p style="font-weight: bold;">Conoscenze acquisite durante il corso:</p>
          <li>Amministrazione e gestione sistemi Unix</li>
          <li>Amministrazione e gestione webserver Apache</li>                    
          <li>Java e programmazione ad oggetti</li>
          <li>Python e programmazione ad oggetti</li>
          <li>HTML</li>
          <li>JavaScript/Jquery e programmazione ad oggetti</li>
          <li>CSS</li>
          <li>PHP</li>
          <li>MySQL</li>
        </ul> 
      </v-flex>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="green darken-1" flat="flat" @click.native="dialog = false">Chiudi</v-btn>          
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-layout>
</template>
    
<script>
  export default {
    data () {
      return {
        dialog: false,
        ueflag: '../static/European_union_flag-128.png',
        itaflag: '../static/Italy_29749.png',
      }
    }
  }
</script>

<style>
ul {
  list-style: inside;
}
</style>