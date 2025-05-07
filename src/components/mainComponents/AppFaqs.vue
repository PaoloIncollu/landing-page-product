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
      ]
    };
  }
}
</script>

<template>
  <section id="list-item-5">
    <div class="mb-5 px-5 d-md-flex">
        <div class="pt-5 pb-sm-4">
        <img src="../../../imgs/single-image2.png" class="img-fluid" alt="">
        </div>
        <div class="ps-md-3">
        <h2>FAQs</h2>
        <div class="accordion" id="accordionExample">
            <!-- Ciclo v-for per generare le accordion items -->
            <div v-for="(faq, index) in faqs" :key="index" class="accordion-item">
            <h2 class="accordion-header">
                <button class="accordion-button collapsed d-flex justify-content-between align-items-center fw-bold" type="button" :data-bs-toggle="'collapse'" :data-bs-target="'#collapse' + index" aria-expanded="false" :aria-controls="'collapse' + index">
                {{ faq.question }}
                <span class="toggle-icon ms-auto"></span>
                </button>
            </h2>
            <div :id="'collapse' + index" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                <div class="accordion-body">
                {{ faq.answer }}
                </div>
            </div>
            </div>
        </div>
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
</style>
