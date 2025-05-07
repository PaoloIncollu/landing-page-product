<script>
export default {
  data() {
    return {
      featuresOne: [
        {
          title: 'Lunga Durata della Batteria',
          description: 'Goditi ore di assenza continua nella risoluzione del bug grazie alla lunga durata della "batteria" (ovvero, la tua pazienza) della paperella di gomma.'
        },
        {
          title: 'Compatibilità Universale',
          description: 'Funziona con tutti i linguaggi di programmazione e sistemi operativi, la paperella di gomma è l\'unico strumento di debugging che non necessita di aggiornamenti.'
        },
        {
          title: 'Design Elegante',
          description: 'Mostra con orgoglio il design elegante e raffinato della tua paperella di gomma, disponibile in vari colori per abbinarsi al tuo stile di programmatore.'
        }
      ],

      featuresTwo: [
        {
          title: 'Resistenza agli Spruzzi',
          description: 'Perfetta per resistere ai piccoli incidenti con caffè e bevande, la tua paperella di gomma non teme schizzi, mantenendoti sempre pronto per il debugging.'
        },
        {
          title: 'Portabilità',
          description: 'Leggera e facile da trasportare, la paperella di gomma può essere il tuo compagno di lavoro ovunque tu vada. Portala con te per un supporto costante.'
        },
        {
          title: 'Promemoria Anti-Stress',
          description: 'Quando lo stress del codice diventa troppo, spremi la tua paperella di gomma per un rapido sollievo anti-stress, senza bisogno di software complicati.'
        }
      ]
    };
  }
}
</script>

<template>
  <div class="info-container text-center d-md-flex px-5 my-5">
    <div class="align-self-center">
      <div v-for="(feature, index) in featuresOne" :key="index">
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>

    <div class="w-100 align-self-center px-4">
      <img src="../../../imgs/invisible.png" class="w-100 " alt="duck">
    </div>

    <div class="align-self-center">
      <div v-for="(feature, index) in featuresTwo" :key="index">
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
</style>
