<script>
export default {
  data() {
    return { 
      
    }
  }
}
</script>

<template>
    <section id="list-item-1">
        <div class="banner-container d-md-flex mb-5">
            
            <div class="banner-img col-md-6">
    
                <img src="../../../imgs/banner-image.png" class="w-100 h-100" alt="">
    
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
    </section>
</template>

<style lang="scss" scoped>
    .banner-image{

        height: auto;
    }

    .banner-bg{

        background-image: url("../../../imgs/banner-bg.png");
        background-size: cover;

        h1{
            font-size: 50px;
        }

        p{

            font-size: 25px;
        }
        
    }
</style>
