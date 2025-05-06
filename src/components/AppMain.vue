<script>
export default {
  data() {
    return {
      testimonials: [
        {
          text: "La paperella di gomma è diventata il mio strumento di debugging preferito...",
          author: "David William - Feb 22, 2023"
        },
        {
          text: "Non avrei mai immaginato quanto una semplice paperella di gomma potesse fare la differenza...",
          author: "Emma Turner - April 5, 2023"
        },
        {
          text: "Da quando ho adottato la paperella di gomma, il mio processo di debugging è migliorato notevolmente...",
          author: "Rachel Bryan - April 18, 2023"
        },
        {
          text: "La mia paperella di gomma è il miglior collega che potessi chiedere...",
          author: "Park C - May 22, 2023"
        }
      ],
      chunkSize: 1 // default per mobile
    };
  },
  computed: {
    groupedTestimonials() {
      const groups = [];
      for (let i = 0; i < this.testimonials.length; i += this.chunkSize) {
        groups.push(this.testimonials.slice(i, i + this.chunkSize));
      }
      return groups;
    }
  },
  mounted() {
    this.updateChunkSize(); // inizializza correttamente
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      this.updateChunkSize();
    },
    updateChunkSize() {
      this.chunkSize = window.innerWidth >= 768 ? 3 : 1;
    }
  }
}
</script>




<template>
    <main>

        <div class="banner-container d-md-flex mb-5">
            
            <div class="banner-img col-md-6">

                <img src="../../imgs/banner-image.png" class="w-100 h-100" alt="">

            </div>

            <div class="banner-bg col-md-6 text-center p-5 d-flex flex-column justify-content-center">

                <h1 class="fw-bold">
                    Rubber Duck Debuggings
                </h1>

                <p>
                    Spiegare il codice a una paperella di gomma aiuta programmatori a chiarire il pensiero e individuare errori nascosti
                </p>
                
                <button class="btn btn-outline-dark fw-bold">
                    AQUISTALA SUBITO!
                </button>

            </div>

        </div>


        <div class="info-container text-center d-md-flex px-5 my-5">

            <div>
                <div>
                    <h3>
                        Lunga Durata della Batteria
                    </h3>

                    <p>
                        Goditi ore di assenza continua nella risoluzione del bug grazie alla lunga durata della "batteria" (ovvero, la tua pazienza) della paperella di gomma.
                    </p>
                </div>
                <div>
                    <h3>
                        Compatibilità Universale
                    </h3>

                    <p>
                        Funziona con tutti i linguaggi di programmazione e sistemi operativi, la paperella di gomma è l'unico strumento di debugging che non necessita di aggiornamenti.
                    </p>
                </div>

                <div>
                    <h3>
                        Design Elegante
                    </h3>

                    <p>
                        Mostra con orgoglio il design elegante e raffinato della tua paperella di gomma, disponibile in vari colori per abbinarsi al tuo stile di programmatore.
                    </p>
                </div>
            </div>
            

            <div class="w-100 align-self-center px-4">
                <img src="../../imgs/invisible.png" class="w-100 " alt="duck">
            </div>

            <div>
                <div>
                    <h3>
                        Resistenza agli Spruzzi
                    </h3>

                    <p>
                        Perfetta per resistere ai piccoli incidenti con caffè e bevande, la tua paperella di gomma non teme schizzi, mantenendoti sempre pronto per il dubugging.
                    </p>
                </div>
                <div>
                    <h3>
                        Portabilità
                    </h3>

                    <p>
                        Leggera e facile da trasportare, la paperella di gomma può essere il tuo compagno di lavoro ovunque tu vada. Portala con te per un supporto costante.
                    </p>
                </div>

                <div>
                    <h3>
                        Promemoria Anti-Stress
                    </h3>

                    <p>
                        Quando lo stress del codice diventa troppo, spremi la tua paperella di gomma per un rapido sollievo anti-stress, senza bisogno di software complicati.
                    </p>
                </div>
            </div>
            
        </div>

        
        <div class="text-center my-5 px-5">

            <h2 class="fw-bold">
                Cosa ne pensano i nostri sviluppatori
            </h2>
            <div id="testimonialCarousel" class="carousel slide" data-bs-wrap="false">
                <div class="carousel-inner">
                    <div v-for="(group, index) in groupedTestimonials" :key="index" :class="['carousel-item', { active: index === 0 }]">
                    <div class="row text-center">
                        <div v-for="(testimonial, i) in group" :key="i" class="col-12 col-md-4 mb-3">
                        <div class="p-3 border rounded h-100">
                            <p>{{ testimonial.text }}</p>
                            <p>
                            <i v-for="n in 5" :key="n" class="fa-solid fa-star text-warning"></i>
                            </p>
                            <p class="fw-semibold">{{ testimonial.author }}</p>
                        </div>
                        </div>
                    </div>
                    </div>
                </div>

                <!-- Pulsanti di navigazione -->
                <button class="carousel-control-prev" type="button" data-bs-target="#testimonialCarousel" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon"></span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#testimonialCarousel" data-bs-slide="next">
                    <span class="carousel-control-next-icon"></span>
                </button>
            </div>
        </div>

  


        
    
    </main>
</template>

<style lang="scss" scoped>

    main{

        margin-top: 100px;
        font-weight: 400;
        line-height: 1.24;
        color: #3D3A38;

        .banner-image{

            height: auto;
        }
        .banner-bg{

            background-image: url("../../imgs/banner-bg.png");
            background-size: cover;
             
        }
    }

    @media (min-width: 1200px){

        h1{
            font-size: 50px;
        }

        p{

            font-size: 25px;
        }
    }

</style>
