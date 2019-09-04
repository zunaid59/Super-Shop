<template>


  <ul class="list-group">Cart
    <li class="list-group-item">
      <span class="item-name">Name</span>
      <span class="item-price float-right">Price</span>
    </li>
    <hr>
    <li v-for="(item,index) in items" :key="index" class="list-group-item">
      <span>{{item.title}}</span>
      <span class="item-price float-right">{{item.price}}</span>
      <button class="btn btn-sm btn-danger" @click="removeItem(index)">-</button>
    </li>
    <hr>
    <li class="list-group-item">
      <span>Total</span>
      <span class="item-price float-right">${{ totalPrice }}</span>
    </li>
  </ul>


</template>

<script>

    export default {
        props:['items'],
        computed:{
            totalPrice(){
                var total = 0;
                this.items.forEach(item=> {
                    total+= parseFloat(item.price)
                });
                return total
            }
        },

        methods:{

            removeItem(index){
                this.$emit('itemRemoved',index)
            }
        }
    }
</script>

<style>


</style>
