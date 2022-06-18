<template>
  <div>
  <div class="relative">  
    <img
      src="../assets/images/sneaker1.jpg"
      alt="sneaker-image"
      class=" rounded-none md:rounded-lg md:h-96 md:w-96 w-full h-full"
    />
    <button
      class="absolute left-3 top-48 bg-white rounded-full h-8 w-8 md:hidden flex justify-center items-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5 items-center"
        viewBox="0 0 20 20"
        fill="currentColor"
      >
        <path
          fill-rule="evenodd"
          d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
    <button
      class="absolute right-3 top-48 bg-white rounded-full h-8 w-8 md:hidden flex justify-center items-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5 items-center"
        viewBox="0 0 20 20"
        fill="currentColor"
      >
        <path
          fill-rule="evenodd"
          d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
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