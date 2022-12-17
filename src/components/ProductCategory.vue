<template>
     <div class="col-md-3">
         <div class="list-group">
                  <button type="button" style="font-size:14px" class="list-group-item list-group-item-action" v-for="product in getPrimaryProductList" :key="product.id">
                    <span class="pull-left" >
                      <img :src="path +'/public/images/' + product.category_icon" style="width:30px"  class="img-reponsive img-rounded">
                    </span>
                    {{product.category_name}}
                  </button>
              </div>
        </div>
</template>

<script>
export default {
    props:['path'],
    computed:{
        getPrimaryProductList(){
        return this.$store.state.primary_category_list
        },
    },
    mounted(){
        this.$store.dispatch("fetchProductList");
        }
}
</script>