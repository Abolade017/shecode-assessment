<template>
  <div>
    <Navbar />
    <MobileNavbar />
    <div class="pt-0 md:pt-20 max-w-5xl mx-auto">
      <div class="flex md:flex-row flex-col items-center space-x-0 md:space-x-24">
        <SneakerImage class="md:block hidden" />
        <slider @next="next" @previous="previous" class="md:hidden">
          <slide
            v-show="visibleSlide===index"
            v-for="(slide,index) in slides"
            :key="slide"
            :index="index"
            :visibleSlide="visibleSlide"
            :direction="direction"
          >
            <img :src="slide" alt="sneaker-image" class="h-96 w-96" />
          </slide>
        </slider>
        <SneakerCompany />
      </div>
    </div>
  </div>
</template>
<script>
import Navbar from "@/components/layout/Navbar.vue";
import MobileNavbar from "@/components/layout/MobileNavbar.vue";
import SneakerCompany from "@/components/SneakerCompany.vue";
import SneakerImage from "@/components/SneakerImage.vue";
import Slider from "@/components/Slider.vue";
import Slide from "@/components/Slide.vue";
export default {
  components: {
    SneakerImage,
    SneakerCompany,
    Navbar,
    MobileNavbar,
    Slider,
    Slide
  },
   data() {
    return {
      slides: [
        // "@/assets/images/sneaker1.jpg",
        //  "@/assets/images/sneaker2.jpg",
        //  "@/assets/images/mojtaba-fahiminia-q7lul0zB0Lg-unsplash.jpg",
        //  "@/assets/images/mojtaba-fahiminia-CQzCMx_wvk4-unsplash.jpg"
        "https://images.unsplash.com/photo-1603808033192-082d6919d3e1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=415&q=80",
        "https://images.unsplash.com/photo-1603808033176-9d134e6f2c74?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=415&q=80",
        "https://images.unsplash.com/photo-1603808033596-5d1fa1629eae?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=415&q=80",
        "https://images.unsplash.com/photo-1603808033587-935942847de4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1412&q=80"
      ],
      visibleSlide: 0,
      direction: "left"
    };
  },
  computed: {
    slideLen() {
      return this.slides.length;
    }
  },
  methods: {
    next() {
      if (this.visibleSlide >= this.slideLen - 1) {
        this.visibleSlide = 0;
      } else {
        this.visibleSlide++;
        this.direction = "left";
      }
    },
    previous() {
      if (this.visibleSlide <= 0) {
        this.visibleSlide = this.slideLen - 1;
      } else {
        this.visibleSlide--;
        this.direction = "right";
      }
    }
  }
};
</script>
// @ is an alias to /src


