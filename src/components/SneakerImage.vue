<template>
  <div>
  <div class="">  
    <img
      src="../assets/images/sneaker1.jpg"
      alt="sneaker-image"
      class=" rounded-none md:rounded-lg h-96 w-96  hidden md:block"
    /> 
    </div>
    <div class="hidden py-6 md:flex items-center space-x-5">
      <img
        id="img"
        :src=" sneaker.pic"
        alt="sneaker_photo"
        class="w-20 h-20 rounded-md"
        v-for="sneaker in sneakers "
        :key="sneaker.id"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sneakers: [
        {
          id: 1,
          pic: require("../assets/images/sneaker1.jpg")
        },
        { id: 2, pic: require("../assets/images/sneaker2.avif") },
        {
          id: 3,
          pic: require("../assets/images/mojtaba-fahiminia-q7lul0zB0Lg-unsplash.jpg")
        },
        {
          id: 4,
          pic: require("../assets/images/mojtaba-fahiminia-CQzCMx_wvk4-unsplash.jpg")
        }
      ]
    };
  }
};
</script>
<style scoped>
#img:hover {
  transition: 1s;
  opacity: 0.2;
  border: 2px solid orange;
}
</style>