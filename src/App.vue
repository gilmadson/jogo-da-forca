<template>
  <div id="app">

    <h1>Jogo da Forca - Gil</h1>

    <section v-if="tela == 'inicio'" id="inicio">
       
      <Formulario v-if="etapa === 'palavra'"
      title='Defina a palavras'
      button='Próximo'
      :action="setPalavra"
      />

      <Formulario  v-if="etapa === 'dica'"
      title='Defina a Dicas' 
      button='Iniciar jogo :)'
      :action="setDica"
      />
      
        
    </section>

    <section v-if="tela == 'jogo'" id="jogo">
      <Jogo />
    </section>

  </div>
</template>

<script>
import './css/global.css';
import Formulario from './components/Formulario.vue';
import Jogo from './components/Jogo.vue';



export default {
    name: "App",
    data() {
        return {
            tela: 'inicio',
            etapa: 'palavra',
            palavra: '',
            dica: '',
        };
    },
    components: { Formulario, Jogo },
    methods:{
      setPalavra: function(palavra){
       this.palavra = palavra;
       this.etapa ='dica';
      },
      setDica: function(dica){
       this.dica = 'jogo';
       this.etapa ='jogo';
      }
    }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
