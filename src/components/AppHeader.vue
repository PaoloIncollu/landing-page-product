<script>
export default {
  data() {
    return { 
      
    }
  }
}
</script>

<template>
  <header>

    <div class="d-flex justify-content-between px-2 py-3">

      <div class="w-25 align-self-center">

        <img src="../../imgs/logo.png" alt="logo">

      </div>

      <div class="align-self-center">

        <button class="btn btn-light btn-sm " type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight">

          <div class="menu-icon">

            <img src="../../imgs/burger-menu-right.png" class="w-100"  alt="menu">

          </div>
        
        </button>

        <div class="offcanvas offcanvas-end w-75" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">

          <div class="offcanvas-header">

            <div class="w-25 align-self-center">

              <img src="../../imgs/logo.png" alt="logo">

            </div>

            <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

          </div>

          <div class="offcanvas-body">
            
            <div>

              <ul class="list-group ">

                <li class="list-group">                  
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-1">Home</a>
                </li>

                <li class="list-group">
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-2">I punti di forza</a>
                </li>

                <li class="list-group">
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-3">Recensioni</a>
                </li>

                <li class="list-group">
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-4">Paperelle</a>
                </li>

                <li class="list-group">
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-3">FAQs</a>
                </li>

                <li class="list-group">
                  <a class="list-group-item list-group-item-action border-0" href="#list-item-4">Newsletters</a>
                </li>

              </ul>

              

              

              

              

              

              


            </div>

          </div>
    
        </div>

      </div>
    
    </div>
      
  </header>

</template>

<style lang="scss" scoped>

header {
  text-align: center;
  font-size: 16px;
  font-weight: 400;
  line-height: 1.5;

  .menu-icon{

    width: 40px;
    
  }
}

h1 {
  color: blue;
}
</style>
