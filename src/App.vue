<template>
  <div id="app">
  <navbar></navbar>



    <div class="container">
      <div class="row">
        <div class="col-md-9">Inventory
         <inventory @newItemAdded="addCartItem" :items="items"></inventory>
        </div>
        <div class="col-md-3">
          <cart :items="cart"></cart>
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
             items:[],
             cart:[{
                 id:1,
                 title:'jagoar',
                 photot:'http://dummyimage.com/155x146.bmp/dddddd/000000',
                 price:10.55,
             }
             ]
         }
    },

     mounted() {

         this.items = data
     },
    methods : {
         addCartItem(item){
             this.cart.push(item)
         }
    }

}
</script>

<style>


</style>
