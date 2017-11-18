<template>
	<v-flex xs12 md5 class="mt-3">
	<div class="mt-1 mb-5" v-for="post in posts" :key="post.title">
	  <v-card class="my-3" hover>
	    <v-card-media	    	
	    	class="blue--text text--darken-3"
				height="110px"
	      style="background-image: contain; background:#292E49;"                    
	      :src="post.imgUrl">
	      <v-container fill-height fluid>
	        <v-layout fill-height>                         
	          <v-flex xs12 align-end flexbox class="text-xs-center"><span class="headline">{{ post.title }}</span>                                 
	           	              
	          </v-flex>
	        </v-layout>
	      </v-container>
	    </v-card-media>
	    <v-card-actions>                   
	      <v-spacer></v-spacer>                    
	    </v-card-actions>
	    <v-card-text style="margin-top:-20px; padding:0;">
	      <v-expansion-panel>
	        <v-expansion-panel-content style="background:#292E49">	        	
	          <div slot="header" 
	            style="font-size: 14px;">	            
	            <v-flex xs12 class="text-xs-center">	            
	            <v-icon small class="blue--text text--darken-1"                            
		          	v-if="post.title === 'Formazione'">
		          	fa-book
			        </v-icon>			          	
			        <v-icon small class="blue--text text--darken-2"                            
		          	v-if="post.title === 'Conoscenze'">
		          	fa-cogs
			        </v-icon>
			        <v-icon small class="blue--text text--darken-2"                            
		          	v-if="post.title === 'Portfolio'">
		          	fa-folder-open
			        </v-icon>			          				          	
		            <!-- <span style="font-size: 14px;" 
		            	class="blue--text text--darken-3">{{ post.title }}</span>-->
	          	</v-flex>
	          </div>	        	        
	          <v-card v-if="post.title === 'Conoscenze'">
	            <v-card-text  style="background:#292E49">
	              <app-know></app-know>
	            </v-card-text>
	            </v-card>
	          <v-card v-else-if="post.title === 'Formazione'">
	            <v-card-text style="background:#292E49" class="white--text">{{ post.content }}
	                <app-dialog></app-dialog>
	                <v-divider></v-divider>
	                <app-section></app-section>	              
	            </v-card-text>
	            </v-card>
	          <v-card v-else>
	          	<v-card-text style="background:#292E49" class="white--text">{{post.content}}</v-card-text>
	          	<app-portfolio></app-portfolio>
	          </v-card>  
	        </v-expansion-panel-content>
	      </v-expansion-panel>      
	    </v-card-text>
	  </v-card>
	</div>
	</v-flex>
</template>

<script>
import Know from './Know.vue';
import Dialog from './Dialog.vue';
import Section from './Section.vue';
import Portfolio from './Portfolio.vue';
export default {
	data () {
		return {
				tucepLink: 'http://www.tucep.org/formazione-e-lavoro/',
        posts: [
          {
            title: "Formazione",
            content: "Ho sempre espresso la passione verso il mondo digitale e dell'\informatica dall'\infanzia e sebbene non abbia ottenuto a livello universitario alcuna Laurea, la passione, la dedizione e l'\impegno verso il settore non è mai cessato, finchè, dopo vari step lavorativi fuori dal settore e la perdita definitiva dell'\occupazione, dal 2015 tramite il Corso di Formazione Professionale per l\'ottenimento della qualifica di Tecnico Specialista in Applicazioni Informatiche per Piccole e Medie Imprese, indetto dal T.U.C.E.P. in Perugia nello stesso anno, ho maturato nuove ed importanti conoscenze verso gli aspetti primari relativi a creare applicazioni in rete in base, commisurate alle esigenze del cliente, il che può essere tradotto nella creazione di siti web ed applicazioni web in generale con linguaggi e strumenti di sviluppo Open Source. Per lo sviluppo di blog e siti web ho approfondito la conoscenza e l'utilizzo del CMS Wordpress (Php / MySql / Apache) mentre da qualche tempo ho iniziato ad approfondire in particolar modo lo studio del linguaggio di scripting JavaScript."            	
          },
          {
            title: 'Conoscenze',
            content: 'Principali linguaggi',
          },
          {
            title: 'Portfolio',
            content: 'Lavori attivi e progetti: ',
          }
        ]
		}
	},
	components: {
		appKnow: Know,
		appDialog: Dialog,
		appSection: Section,
		appPortfolio: Portfolio
	}
}
</script>

<style scoped>
 a {
 	text-decoration: none;
 	font-size: 14px!important;
 }
li {	
font-family:sans-serif;	
}
</style>