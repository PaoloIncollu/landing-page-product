<script>
export default {
  data() {
    return {
        faqs: [
            {
            question: "Come posso utilizzare la paperella di gomma per il debugging?",
            answer: "Il rubber duck debugging è semplice: spiega il tuo codice alla paperella di gomma come se fosse un collega..."
            },
            {
            question: "Quali sono i vantaggi di usare una paperella di gomma per i programmatori?",
            answer: "La paperella di gomma aiuta i programmatori a pensare in modo critico e a verbalizzare i problemi..."
            },
            {
            question: "Posso usare la paperella di gomma indipendentemente dal linguaggio di programmazione che utilizzo?",
            answer: "Assolutamente sì! La paperella di gomma è universale e funziona con qualsiasi linguaggio di programmazione..."
            },
            {
            question: "Quanto dettagliatamente devo spiegare il mio codice alla paperella di gomma?",
            answer: "Dovresti spiegare ogni dettaglio del tuo codice. Più sei dettagliato, più è probabile che tu scopra errori..."
            }
        ],
      
        features: [
            {
                icon: "../../../imgs/balloon.png",
                alt: "balloon",
                title: "100% Prodotto Di Qualità",
                description: "Abbiamo anche la possibilità di ritiro direttamente dallo stagno"
            },
            {
                icon: "../../../imgs/bag.png",
                alt: "bag",
                title: "Spedizione Gratuita",
                description: "Dal magazzino alla scrivania"
            },
            {
                icon: "../../../imgs/band.png",
                alt: "band",
                title: "Rimborso Garantito",
                description: "Ti rimborsiamo se la paperella fa quack"
            }
        ]
    };
}
}
</script>

<template>
  <section id="list-item-5">
    <div class="mb-5 pt-5 px-5 d-md-flex">
        <div class="pt-5 pb-sm-4 col-md-6">
        <img src="../../../imgs/single-image2.png" class="img-fluid" alt="">
        </div>
        <div class="ps-md-3 col-md-6">
        <h2>FAQs</h2>
        
        <div class="accordion pt-3" id="accordionExample">
            <!-- Ciclo v-for per generare le accordion items -->
            <div v-for="(faq, index) in faqs" :key="index" class="accordion-item">
            <h2 class="accordion-header">
                <button class="accordion-button collapsed d-flex justify-content-between align-items-center fw-bold fs-5" type="button" :data-bs-toggle="'collapse'" :data-bs-target="'#collapse' + index" aria-expanded="false" :aria-controls="'collapse' + index">
                {{ faq.question }}
                <span class="toggle-icon ms-auto"></span>
                </button>
            </h2>
            <div :id="'collapse' + index" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                <div class="accordion-body fs-6">
                {{ faq.answer }}
                </div>
            </div>
            </div>
        </div>
        </div>
    </div>

    <div class="mb-5 p-5 d-md-flex justify-content-between">
  <div
    v-for="(feature, index) in features"
    :key="index"
    class="d-flex flex-column text-center col-md-4 px-3"
    :class="{ 'custom-border-md': index === 1 }"
  >
    <div class="icon align-self-center">
      <img :src="feature.icon" :alt="feature.alt" class="w-100" />
    </div>

    <h3 class="fw-bold">
      {{ feature.title }}
    </h3>

    <p>
      {{ feature.description }}
    </p>
  </div>
</div>

  </section>
</template>

<style lang="scss" scoped>



  /* Rimuove la freccia predefinita di Bootstrap */
  .accordion-button::after {
    display: none;
  }

  /* Simbolo personalizzato */
  .accordion-button .toggle-icon::before {
    content: "+";
    font-size: 1.25rem;
    font-weight: bold;
    padding-left: 10px;
  }

  /* Cambia simbolo in "–" quando aperto */
  .accordion-button:not(.collapsed) .toggle-icon::before {
    content: "–";
  }

  .accordion-button {
    background-color: transparent !important;
    color: inherit !important;
    box-shadow: none !important;
    border: none !important;
  }

  .accordion-button:hover,
  .accordion-button:focus {
    background-color: transparent !important;
    color: inherit !important;
    box-shadow: none !important;
  }

  .accordion-button:not(.collapsed) {
    background-color: transparent !important;
    color: inherit !important;
    box-shadow: none !important;
  }

  .icon{

    width: 50px;
  }

  @media (min-width: 768px) {
  .custom-border-md {
    border-left: 1px solid #D2D2D2;
    border-right: 1px solid #D2D2D2;
  }
}

</style>
