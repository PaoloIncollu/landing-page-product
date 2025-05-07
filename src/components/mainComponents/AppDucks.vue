<script>
export default {
  data() {
    return {
      ducks: [
        {
          image: "../../../imgs/product-item1.png",
          name: "Cool-duck",
          price: 15,
          rating: 5
        },
        {
          image: "../../../imgs/product-item2.png",
          name: "Classic-duck",
          price: 29,
          rating: 5
        },
        {
          image: "../../../imgs/product-item3.png",
          name: "Bat-duck",
          price: 69,
          rating: 5
        }
      ]
    };
  }
}
</script>

<template>
    <section id="list-item-4">
        <div class="ducks-container text-center">
            <h2>
            La collezione di paperelle
            </h2>
            <p>
            Una paperella per ogni stile di programmazione
            </p>
            <div class="d-flex flex-column flex-md-row justify-content-center justify-content-md-start text-center text-md-start g-3 mt-5 mx-5">
            <div v-for="(duck, index) in ducks" :key="index" class="pb-sm-3 px-md-3">
                <img :src="duck.image" :alt="`item-${index + 1}`" class="img-fluid">
                <p class="text-start pt-3">
                <!-- Visualizza le stelle in base alla valutazione -->
                <i v-for="n in duck.rating" :key="n" class="fa-solid fa-star text-warning"></i>
                <br>
                <i class="fw-bold">{{ duck.name }}</i>
                <br>
                <i class="price-duck fw-bold">€{{ duck.price }}</i>
                </p>
            </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    .ducks-container {
    h2 {
        font-size: 50px;
    }

    p {
        font-size: 25px;
    }

    .price-duck {
        color: #04DF6C;
    }
    }
</style>
