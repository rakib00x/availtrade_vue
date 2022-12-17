<template>
    <div class="col-md-6">
            <MDBCarousel
              v-model="carousel4"
              :items="items4"
            />
        </div>
</template>

<script>
  import { ref } from "vue";
  import { MDBCarousel } from "mdb-vue-ui-kit";
export default {
    components:{
        MDBCarousel
    },
    setup() {
      const items4 = [
        {
          src: "https://www.availtrade.com/public/images/1647422715426Screenshot_2.png",
          alt: "..."
        },
        {
          src: "https://www.availtrade.com/public/images/1647422533576Screenshot_1.png",
          alt: "..."
        },
        {
          src: "https://www.availtrade.com/public/images/1647423019322Screenshot_3.png",
          alt: "..."
        }
      ];
      const carousel4 = ref(0);
      return {
        items4,
        carousel4
      };
    },
}
</script>