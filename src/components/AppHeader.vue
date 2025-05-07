<script>
export default {
  data() {
    return {
      menuItems: [
        { label: 'Home', href: '#list-item-1' },
        { label: 'I punti di forza', href: '#list-item-2' },
        { label: 'Recensioni', href: '#list-item-3' },
        { label: 'Paperelle', href: '#list-item-4' },
        { label: 'FAQs', href: '#list-item-5' },
        { label: 'Newsletters', href: '#list-item-6' },
      ]
    }
  },
  mounted() {
    // Impedisci al browser di fare lo scroll automatico sull'hash dopo il reload
    if ('scrollRestoration' in history) {
      history.scrollRestoration = 'manual';
    }

    // Se c'è un hash, rimuovilo subito e forzatamente scrolla su
    if (window.location.hash) {
      // Rimuove l'hash dall'URL
      history.replaceState(null, '', window.location.pathname + window.location.search);

      // Forza lo scroll all'inizio in modo affidabile
      setTimeout(() => {
        window.scrollTo({ top: 0, behavior: 'instant' }); // oppure 'auto'
      }, 1); // Questo forza lo scroll dopo che il browser ha fatto il suo
    }
  },
  methods: {
      closeOffcanvas() {
        const offcanvasElement = document.getElementById('offcanvasRight');
        const offcanvas = new bootstrap.Offcanvas(offcanvasElement);
        offcanvas.hide(); // Chiude l'offcanvas
      }
    }
}
</script>

<template>
  <header class="position-fixed z-3 top-0 start-0 w-100">
    <div class="d-flex justify-content-between px-2 py-3">
      <!-- Logo -->
      <div class="w-25 align-self-center">
        <img src="../../imgs/logo.png" alt="logo">
      </div>

      <!-- Burger Menu: fino a MD -->
      <div class="align-self-center d-lg-none">
        <button class="btn btn-light btn-sm" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight">
          <div class="menu-icon">
            <img src="../../imgs/burger-menu-right.png" class="w-100" alt="menu">
          </div>
        </button>
      </div>

      <!-- Menu orizzontale: solo da LG in poi -->
      <div class="d-none d-lg-block align-self-center">
        <ul class="list-group list-group-horizontal gap-3 mb-0">
          <li v-for="(item, index) in menuItems" :key="index">
            <a class="list-group-item list-group-item-action border-0" :href="item.href">
              {{ item.label }}
            </a>
          </li>
        </ul>
      </div>
    </div>

    <!-- Offcanvas: solo per mobile -->
    <div class="offcanvas offcanvas-end w-75" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">
      <div class="offcanvas-header">
        <div class="w-25 align-self-center">
          <img src="../../imgs/logo.png" alt="logo">
        </div>
        <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>

      <div class="offcanvas-body">
        <ul class="list-group">
          <li v-for="(item, index) in menuItems" :key="'mobile-' + index">
            <a
              class="list-group-item list-group-item-action border-0"
              :href="item.href"
              @click="closeOffcanvas"
            >
              {{ item.label }}
            </a>
          </li>
        </ul>
      </div>
    </div>

  </header>
</template>

<style lang="scss" scoped>
header {
  height: 100px;
  text-align: center;
  font-size: 16px;
  font-weight: 400;
  line-height: 1.5;
  background-color: white;

  .menu-icon {
    width: 40px;
  }

  ul {
    padding-left: 0;
    list-style: none;
  }

  .list-group-item {
    background-color: transparent;
    color: black;
    cursor: pointer;

    &:hover {
      text-decoration: underline;
    }
  }
}
</style>
