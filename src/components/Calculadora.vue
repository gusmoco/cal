<template>
<div id="appCalc">
	<main class="principal">
		<section class="inputs">
			<p class="input">{{ result }}</p>
			<input class="input" type="number" v-model.number="valor1">
			<input class="input" type="number" v-model.number="valor2">
			<input class="input" type="operator" v-model.name="operador">
		</section>
		<section class="botoes">
			<button class="botao" @click="calc()">+</button>
			<button class="botao" @click="calc('divisao')">÷</button>
			<button class="botao" @click="calc('subtaçao')">-</button>
			<button class="botao" @click="calc('multiplicaçao')">×</button>
		</section>
	</main>
</div>
</template>
<script>
	export default{
		name:'Calculadora',
		data(){
			return{
			 	valor1:'',
			 	valor2:'',
			 	operator:'',
			 	result:'',
			 	visor: 0,
			}
		},
		methods:{
			calc(){
				if ( this.operator === 'soma'){
					this.result = this.valor1 + this.valor2
				}else if(operator === 'subtaçao'){
					this.result = this.valor1 - this.valor2
				}else if (operator === 'multiplicaçao'){
					this.result = this.valor1 * this.valor2
				}else{
					this.result = this.valor1 / this.valor2
				}
			},
			write(number){
				if (this.operator === ''){
					this.valor1 = this.valor1 + number
					this.visor = this.valor1
				}else{
					this.valor2 = this.valor2 + number
					this.visor = this.valor2
				}
			},
			setOperator(value){
				this.operator = value
			},
			restart(){
				this.valor1 = ''
				this.valor2 = ''
				this.operator = ''
				this.result = ''
			}
		}
	}
</script>
<style scoped>
	*{
		margin:0;
		padding: 0;
	}
	#appCalc{
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.principal{
		max-width: 300px;
		background: #2A3137;
		color: #6FB0E2;
	}

	.titulo{
		color: #6FB0E2;
	}
	.input{
		width: 100%;
		padding:20px;
		margin: 5px;
		border: none;
		background: #9EA2A6;
		color: #2A3137;
		
		
	}
	.botoes{
		display: flex;
		flex-wrap: wrap;
		margin: 0;
		padding: 0;
	}
	.botao{
		background: #2A3137;
		color: #6FB0E2;
		padding:20px;
		border: none;
		width: 150px;
		height: 150px;		
	}
</style>