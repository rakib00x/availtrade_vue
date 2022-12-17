<template>
  <div>
    <h3 class="my-4">Just For You</h3>
    <div class="row row-cols-1 row-cols-sm-3 row-cols-md-5">
        <div class="col" v-for="product in getJustForYou" :key="product.id">
          <div class="card p-3" style="height: 22rem;">
            <img :src="path +'/public/images/' + product.products_image" class="card-img-top" alt="...">
            <div class="card-body">
            <h6 class="card-title">{{product.product_name.substring(0,20)+".."}}</h6>
            <p class="card-text">৳ {{product.product_price}}</p>
            <p class="card-text">{{product.unit}} Pices (Min Order)</p>
            <p class="text-end">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-eye me-2" viewBox="0 0 16 16">
              <path d="M16 8s-3-5.5-8-5.5S0 8 0 8s3 5.5 8 5.5S16 8 16 8zM1.173 8a13.133 13.133 0 0 1 1.66-2.043C4.12 4.668 5.88 3.5 8 3.5c2.12 0 3.879 1.168 5.168 2.457A13.133 13.133 0 0 1 14.828 8c-.058.087-.122.183-.195.288-.335.48-.83 1.12-1.465 1.755C11.879 11.332 10.119 12.5 8 12.5c-2.12 0-3.879-1.168-5.168-2.457A13.134 13.134 0 0 1 1.172 8z"/>
              <path d="M8 5.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5zM4.5 8a3.5 3.5 0 1 1 7 0 3.5 3.5 0 0 1-7 0z"/>
              </svg>{{product.visitor_count}}
            </p>
            
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
         getJustForYou(){
            return this.$store.state.just_for_you
         },
    },
    mounted(){
        this.$store.dispatch("fetchJustForYou");
    }
}
</script>

