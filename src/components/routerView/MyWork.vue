<template>
<section id="wrapping">
    <div class="py-3" v-for="(sample,index) in workSamples" :key="index">
        <div class="container WhiteBg">
            <div class="row mt-5 mx-3 py-3 displayNone animated">
                <div class="col-md-6 animated" :class=" {'order-2': index%2}">
                    <div class="row">
                        <div class="col text-center">
                            <h4 class="text-info"> {{ sample.title }} </h4>
                            <p>
                                <u> DESCRIPTION:</u>
                                <span> {{ sample.description }}</span>
                            </p>
                            <a :href=sample.github_link target="_blank" class="btn btn-block button-outline-purple" style="color:white">
                                <span>See on </span>
                                <i class="fab fa-github"></i>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 d-none d-md-block animated">
                    <div class="card border-0">
                        <div class="card-img">
                          <a :href=sample.github_link target="_blank" style="text-decoration: none">
                            <i class="fab fa-github" style="font-size:150px; text-align: center; display: block"></i>
                          </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
</template>

<script>
import { animateMixin } from '../Globalfunction';
export default {
  data: function() {
    return {
      workSamples: {
        1: {
          title: "Customers-Orders",
          description:
            "Awesome angular application that shows list of customers and their orders",
          github_link: "https://github.com/Zeks92/Customers-Orders"
        },
        2: {
          title: "Diary",
          description:
            "Personal diary application developed with Nuxt to save your events,shoppings and news",
          github_link: "https://github.com/Zeks92/Diary"
        },
        3: {
          title: "Quiz",
          description:
            "A quiz app built with Vue.js and powered by the Open Trivia Database.",
          github_link: "https://github.com/Zeks92/Quiz"  
        },
        4: {
          title: "BestBuyShop",
          description:
            "MEVN stack shopping cart with add,edit and delete products in the shop.",
          github_link: "https://github.com/Zeks92/BestBuyShop"
        },
        5: {
          title: "TopMoviesList",
          description:
            "A Vue.js application that show movies list. Using axios get request, myjson api retrieves all movie data. Order movies by few categories, quick filter through list and many more exciting options in this app",
          github_link: "https://github.com/Zeks92/TopMoviesList"
        },
        6: {
          title: "Memory Game",
          description:
            "Simple blocks match game developed with Vanilla JS. Match all 36 blocks in a less moves as possible to get 5stars",
          github_link: "https://github.com/Zeks92/MemoryGame"
        },
        7: {
          title: "SpeedType",
          description: "Speedtyping game with three levels of difficulty. Developed with Vanilla JS and Particles.js used for background snow effect",
          github_link: "https://github.com/Zeks92/SpeedType"
        },
      }
    };
  },
  mounted() {
    let sample_cmp = document.getElementsByClassName("WhiteBg");
    this.mouseenterFadeInTarget(sample_cmp)
  },
  mixins: [animateMixin]
};
</script>

<style scoped>
#wrapping {
  background-image: linear-gradient(-20deg, #b721ff 0%, #21d4fd 100%);
}
.displayNone {
  /* background: red; */
  visibility: hidden;
}
.WhiteBg {
  background: #fff;
  box-shadow: 2px 4px 20px rgba(0, 0, 0, 0.2);
  transition-duration: 0.7s;
}
.WhiteBg:hover {
  border-radius:10px;
}
.button-outline-purple {
  border: 2px solid #5c46af;
  color: black !important;
}

.button-outline-purple:hover {
  background: #5c46af;
  color: white !important;
  border-radius: 10px;
}
</style>
