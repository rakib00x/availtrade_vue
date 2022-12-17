<template>
    <div class="col-md-3">
          <h4>EveryThing In One Place</h4>
          <div class="card mb-3" style="border: none" v-for="product in getThreeProduct" :key="product.id">
          <div class="row g-0">
            <div class="col-md-4">
              <img :src="path +'/public/images/' + product.products_image" class="img-fluid rounded-start" alt="...">
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">{{product.product_name.substring(0,20)+"..."}}</h5>
                <button class="btn btn-success">Source</button>
              </div>
            </div>
          </div>
          </div>
        </div>
</template>

<script>
export default {
    props:['path'],
    computed:{
         getThreeProduct(){
            return this.$store.state.right_three_product
        },
    },
    mounted(){
        this.$store.dispatch("fetchRightThreeProduct");
    }
}
</script>