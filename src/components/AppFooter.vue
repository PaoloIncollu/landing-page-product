<script>
export default {
  data() {
    return {
      socialIcons: [
        { href: '#', iconClass: 'fa-facebook-f' },
        { href: '#', iconClass: 'fa-twitter' },
        { href: '#', iconClass: 'fa-youtube' },
        { href: '#', iconClass: 'fa-linkedin-in' },
        { href: '#', iconClass: 'fa-instagram' }
      ]
    };
  }
}
</script>

<template>
  <section id="list-item-6">
    <footer>
      <div class="footer-top text-center p-5">
        <h2>
          Iscriviti per rimanere aggiornato
        </h2>

        <p>
          Iscriviti alla nostra newsletters per rimanere aggiornato su sconti e novità
        </p>

        <div class="container my-4">
            <div class="input-wrapper w-md-50 d-flex align-items-center border-bottom pb-2 position-relative">
                <input 
                type="email" 
                class="form-control email-input" 
                placeholder="Lascia la tua email qui..." 
                >
                <i class="fa-solid fa-paper-plane fa-xl letter-icon position-absolute end-0 me-2"></i>
            </div>
        </div>


        <div class="d-flex justify-content-center">
          <a
            v-for="(item, index) in socialIcons"
            :key="index"
            :href="item.href"
          >
            <i :class="['fa-brands', item.iconClass, 'fa-2xl', 'icon']"></i>
          </a>
        </div>
      </div>

      <div class="footer-bottom text-center p-2">
        <h5>
          <i class="fa-regular fa-copyright"></i>
          BooLanding Product. Designed by Boolean
        </h5>
      </div>
    </footer>
  </section>
</template>

<style lang="scss" scoped>
    .footer-top {
        background-color: #d2d2d2;

        h2 {
            font-size: 50px;
        }

        p {
            font-size: 25px;
        }

        a {
            text-decoration: none;
        }

        .email-input {
            border: none;
            box-shadow: none;
            padding-left: 0;
            background-color: #d2d2d2; 
            
        }

        .input-wrapper {
            margin: 0 auto;
            background-color: #d2d2d2; 
            padding-right: 40px; 

            .letter-icon{

                color: #04df6c;
            }
        }

        .input-wrapper input::placeholder {
            color: #666;
        }


        .icon {
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #04df6c;
            border: 1px solid grey;
            border-radius: 50%;
            margin: 0 10px;
        }
    }

    @media (min-width: 768px) {
    .input-wrapper {
        width: 60%;
    }
    }

</style>
