<template>
  <div class="home">
    <div class="container">
      <div class="row">
       <ProductCategory 
       :path="path"
       />
        <Slider />
        <RightThreeProduct 
        :path="path"
         />
      </div>
      <JustForYou 
      :path="path"
      />
    </div>
  </div>
  <div>
  </div>
  <ul>
    <li v-for="cat in getCategory" :key="cat.id">{{cat.tartiary_category_name}}</li>
  </ul>
  <div class="container">
     <ul class="navbar-nav">
       <li class="nav-item dropdown has-megamenu">
				<a class="nav-link dropdown-toggle" href="#" data-bs-toggle="dropdown"> Mega menu  </a>
				<div class="dropdown-menu megamenu" role="menu">
					<div class="row g-3">
						<div class="col-lg-3 col-6" v-for="product in getSecondaryCategoryList" :key="product.id">
							<div class="col-megamenu">
								<h6 class="title">{{product.secondary_category_name}}</h6>
								<ul class="list-unstyled">
									<li><a href="#">Custom Menu</a></li>
									<li><a href="#">Custom Menu</a></li>
									<li><a href="#">Custom Menu</a></li>
									<li><a href="#">Custom Menu</a></li>
									<li><a href="#">Custom Menu</a></li>
								</ul>
							</div>  <!-- col-megamenu.// -->
						</div><!-- end col-3 -->
					</div><!-- end row --> 
				</div> <!-- dropdown-mega-menu.// -->
			</li>
  </ul>
  </div>
</template>

<script>
  import ProductCategory from '../components/ProductCategory.vue'
  import RightThreeProduct from '../components/rightThreeProducts.vue'
  import JustForYou from '../components/JustForYou.vue'
  import Slider from '../components/Slider.vue'

export default {
  name: 'Home',
  components: {
      ProductCategory,
      RightThreeProduct,
      JustForYou,
      Slider
    },
    
  data(){
    return{
      path:'https://www.availtrade.com'
    }
  },
 
  computed:{
    getSecondaryCategoryList(){
      return this.$store.state.sCategoryList
    },
    getCategory(){
      return this.$store.getters.tertiarycategoryID
    }

  },
  mounted(){
    this.$store.dispatch("fetchSecondaryTertiaryCatgeoryList");
  }
}
</script>
