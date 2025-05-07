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
      
    }
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
    <section id="list-item-3">
        <div class="reviews-container text-center my-5 px-5">
            <h2 class="fw-bold py-5">
                Cosa ne pensano i nostri sviluppatori
            </h2>
            <div id="testimonialCarousel" class="carousel slide" data-bs-wrap="false">
                
                <!-- PALLINI INDICATORI -->
                <div class="carousel-indicators">
                    <button
                        v-for="(group, index) in groupedTestimonials"
                        :key="index"
                        type="button"
                        data-bs-target="#testimonialCarousel"
                        :data-bs-slide-to="index"
                        :class="{ active: index === 0 }"
                        :aria-current="index === 0 ? 'true' : null"
                        :aria-label="`Slide ${index + 1}`"
                    ></button>
                </div>

                <div class="carousel-inner pb-3">
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
                    <span class="carousel-control-prev-icon text-black"></span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#testimonialCarousel" data-bs-slide="next">
                    <span class="carousel-control-next-icon"><i class="fa-regular fa-circle-right"></i></span>
                </button>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.reviews-container{

    h2{
        font-size: 50px;
    }

    .carousel-indicators [data-bs-target] {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        background-color: #ccc; /* pallini inattivi */
        margin: 0 6px;
        border: none;
        opacity: 1;
    }

    .carousel-indicators .active {
        background-color: #0d6efd; /* pallino attivo */
        
    }
}
</style>
