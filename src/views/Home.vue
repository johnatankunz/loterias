<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
         <ion-title id="title">Gerador de 6 dezenas para loterias</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
           <ion-title size="large" id="title">Gerador de 6 dezenas para loterias</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-input type="text" id="dezenas" disabled>{{primeiraDezena}} - {{segundaDezena}} - {{terceiraDezena}} - {{quartaDezena}} - {{quintaDezena}} - {{sextaDezena}}</ion-input>
    <ion-button expand="block" @click="generated()">Clique aqui para gerar os números da sorte</ion-button>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar
  },
  data(){
    return{
      primeiraDezena: '',
      segundaDezena: '',
      terceiraDezena: '',
      quartaDezena: '',
      quintaDezena: '',
      sextaDezena: '',
     
    }
  },
  methods: {
   

    generated: function(){

      const dezenas = [];

      while (dezenas.length < 6) {
        const numeroSorteado = Math.floor(Math.random() * 60 + 1).toString();

        if (dezenas.indexOf(numeroSorteado) == -1)
            dezenas.push(numeroSorteado);
    }
     this.primeiraDezena = dezenas[0];
     this.segundaDezena = dezenas[1];
     this.terceiraDezena = dezenas[2];
     this.quartaDezena = dezenas[3];
     this.quintaDezena = dezenas[4];
     this.sextaDezena = dezenas[5];
  
    }
  }
});
</script>

<style scoped>
#title{
font-size: 25px;
text-align: center;
}
#dezenas{
  text-align: center;
  font-size: 50px;
  margin-left: 35%;
  margin-right: 35%;
}
</style>