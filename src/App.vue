<template>
  <div id="app">
  <navbar></navbar>



    <div class="container">
      <div class="row">
        <div class="col-md-9">Inventory
         <inventory :items="items"></inventory>
        </div>
        <div class="col-md-3">
          <cart></cart>
        </div>
      </div>
    </div>

  </div>

</template>

<script>

  import Cart from './components/Cart'
  import Navbar from './components/Navbar'
  import Inventory from './components/Inventory'
  import data from "./data.js";

export default {
     components:{
         Navbar,
         Cart,
         Inventory
     },

    data(){
         return {
             items:[]
         }
    },

     mounted() {

         this.items = data
     }

}
</script>

<style>


</style>
