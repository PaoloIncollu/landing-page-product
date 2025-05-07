<script>
export default {
  data() {
    return { 
      
    }
  }
}
</script>

<template>
  <header class="position-fixed z-3 top-0 start-0 w-100">
    <div class="d-flex justify-content-between  px-2 py-3">

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
          <li><a class="list-group-item list-group-item-action border-0" href="../../index.html">Home</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="./mainComponents/AppInfo.vue">I punti di forza</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-3">Recensioni</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-4">Paperelle</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-5">FAQs</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-6">Newsletters</a></li>
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
          <li><a class="list-group-item list-group-item-action border-0" href="../../index.html">Home</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-2">I punti di forza</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-3">Recensioni</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-4">Paperelle</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-5">FAQs</a></li>
          <li><a class="list-group-item list-group-item-action border-0" href="#list-item-6">Newsletters</a></li>
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
