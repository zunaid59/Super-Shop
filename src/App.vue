<template>
  <div id="app">
    <router-link :to="{path:'/'}">Home</router-link>
    <router-link :to="{path:'/test'}">Test</router-link>
    <router-view> </router-view>
<!--  <navbar @search="search"></navbar>-->



<!--    <div class="container">-->
<!--      <div class="row">-->
<!--        <div class="col-md-9">Inventory-->
<!--         <inventory @newItemAdded="addCartItem" :items="items"></inventory>-->
<!--        </div>-->
<!--        <div class="col-md-3">-->
<!--          <cart :items="cart" @itemRemoved="removedItem"></cart>-->
<!--        </div>-->
<!--      </div>-->
<!--    </div>-->

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
             cart:[
             ]
         }
    },

     mounted() {

         this.items = data
     },
    methods : {

         search(keyword){

             this.items=data.filter(item=>{

                 return item.title.toLowerCase().indexOf(keyword.toLowerCase()) !== -1

             })

         },

         addCartItem(item){
             this.cart.push(item)
         },

        removedItem(index){
             this.cart.splice(index,1)
        }


    }

}
</script>

<style>


</style>
