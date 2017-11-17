<template>
	<div>
		<section>Continuando in maniera autonoma il percorso iniziato, sto portando avanti lo studio e la pratica nell'implementazione di applicazioni web progressive (PWA) e applicazioni web su singola pagina (SPA) attraverso il linguaggio JavaScript,  utilizzando per una continua e giusta formazione nel settore <span style="font-weight:bold">autorevoli corsi a pagamento</span> dai quali ho tratto nuove e significative compentenze nell'\amibto dello sviluppo di applicazioni web.</section> 
  <small><a :href="udemylinkjs">corso Udemy JavaScript</a> | 
  <a :href="udemylinknode">corso Udemy Node.js</a> |  	
  <a :href="udemylinkvue">corso Udemy Vue.js</a>	
  </small>
	</div>	
</template>

<script>
	export default {
		data () {
			return {
				udemylinkjs: 'https://www.udemy.com/the-complete-javascript-course/',
				udemylinknode: 'https://www.udemy.com/the-complete-nodejs-developer-course-2',
				udemylinkvue: 'https://www.udemy.com/vuejs-2-the-complete-guide/'
			}
		}
	}
</script>
