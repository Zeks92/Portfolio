<template>
<div id="wrapper" style="overflow:hidden">
    <section id="part-1" class="animated parralax d-none d-md-block mouseenterAnimate">
        <div class="row quote animated bounceIn"></div>
    </section>
    <section id="part-2" class="mouseenterAnimate">
        <div class="container py-5 displayNone animated">
            <div class="row text-center">
                <h3 class="col-md-8 display-4" style="color: #e60000">
                    <div> Hey, my name is
                        <p style="color: #ebebe0">{{ name }}.</p>
                    </div>
                    <div>I am a
                      <vue-typer :text=profile></vue-typer>
                    </div>
                </h3>
                <div class="col-md-4 d-none d-md-block">
                    <div class="avatar transitionDuration"></div>
                    <!-- border-radius : 50%; -->
                </div>
            </div>
        </div>
    </section>
    <section id="part-3" class="mouseenterAnimate">
        <div class="container displayNone animated">
            <div class="row my-4">
                <div class="col text-center">
                    <h3 class="display-3 heading"> Skill Set </h3>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-4 mb-3" v-for="(skill, index) in skillsCard.skills" :key="index">
                    <div class="card border-0">
                        <div class="card-body text-center">
                            <h5 class="card-tittle">
                                {{ skill }}
                                <!-- Add more skills in the data(){ .. } inside the card-data obj -->
                            </h5>
                            <div class="row">
                                <!-- animated cards with hover effect -->
                                <div class="col-md-8 offset-md-2">
                                    <div class="card-text">
                                        <p class="exp text-info"> {{ skillsCard.experianceYear[index] }}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section id="part-4" class="mouseenterAnimate">
        <div class="container displayNone animated">
            <div class="row my-5">
                <h3 class="col-sm-10 offset-sm-1 text-center heading display-3 text-danger">
                    My Best Works
                </h3>
            </div>
            <div class="row" style="justify-content: center">
                <div class="col-sm-3 my-3" v-for="(work,index) in workPrevious" :key="index">
                    <div class="card text-center border-0 hoverEffect transitionAnimated" style="background-color: #e6e6e6;height: 340px;">
                        <div class="card-body">
                            <div class="card-title text-info my-2">
                                <h4>
                                    {{ work.title }}
                                </h4>
                            </div>
                            <div class="card-subtitle  text-justify">
                                {{ work.description }}
                            </div>
                        </div>
                        <div class="card-footer">
                           <a :href=work.githubLink target="_blank" class="btn btn-block button-outline-purple">
                                View on
                                <i class="fab fa-github"></i>
                            </a>     
                        </div>    
                    </div>
                </div>
            </div>
            <hr>
            <div class="row text-center pb-5">
                    <div class="offset-md-4 col-md-4">
                        <router-link :to="{ name: 'portfolio' }" style="text-decoration: none"> 
                                Work Preview Page
                        </router-link>
                    </div>
                </div>
            </div>
    </section>
</div>
</template>

<script>
import { VueTyper } from "vue-typer";
import { animateMixin } from "../Globalfunction.js"
export default {
  data() {
    return {
      homeQuotation: "Welcome",
      name: "Zeljko Lazovic",
      profile: "Frontend Developer",

      skillsCard: {
        skills: [
          "HTML",
          "CSS",
          "Bootstrap",
          "Sass",
          "JavaScript",
          "Vue",
          "Nuxt",
          "Angular",
          "Kendo"
        ],
        experianceYear: [
          "4 years",
          "4 years",
          "3 years",
          "3 years",
          "3 years",
          "3 years",
          "2 years",
          "2 years",
          "2 years"
        ]
      },

      conditionBool_profile: false,
      star: false,
      active: false,
      // star is responsible to add ** to vue's card and boostrap's at top-right  -> my best

      workPrevious: {
        1: {
          prevImage: "",
          title: "Customers-Orders",
          description:
            "Awesome angular application that shows list of customers and their orders",
          githubLink: "https://github.com/Zeks92/Customers-Orders"
        },
        2: {
          prevImage: "",
          title: "Diary",
          description:
            "Personal diary application developed with Nuxt to save your events,shoppings and news",
          githubLink:
            "https://github.com/Zeks92/Diary"
        }
      }
    };
  },
  components: {
    VueTyper
  },
  mounted() {
    var sample_cmp = document.getElementsByClassName("mouseenterAnimate");
    this.mouseenterFadeInTarget(sample_cmp)    
  },
  mixins: [ animateMixin ]
};
</script>

<style scoped>
.displayNone {
  visibility: hidden;
}
@media screen (min-width: 1000px) {
  #part-2 {
    height: 100vh;
  }
}

.transitionDuration {
  transition-duration: 1s;
}
#part-1 .quote {
  background: url("../../assets/images/homeQuote.png");
  background-attachment: fixed;
  background-repeat: no-repeat;
  height: 100%;
  width: 100%;
  background-position: center;
}
.parralax {
  background: url("../../assets/images/home.jpg");
  background-attachment: fixed;
  background-size: cover;
  background-position: center;
  height: 100vh;
  background-repeat: no-repeat;
}

.cardHover:hover {
  transform: scale(2.0);
}
.heading {
  color: blueviolet;
  border-bottom: 1px dashed;
}

#part-2 {
  background-image: linear-gradient(to top, #37ecba 0%, #72afd3 100%);
  padding-top:10%;
}
.avatar {
  background-image: url("../../assets/images/ja.jpg");
  border: 1px solid #fff;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  height: 100%;
}
.avatar:hover {
  border-radius: 20px;
}
#part-3 .card,
#part-4 .card {
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.3);
  transition-duration: 0.25s;
}

#part-3 .card:hover {
  transform: scale(0.95);
}

#part-4 {
  background-image: linear-gradient(to bottom, #88d3ce 0%, #6e45e2 100%);
}
#part-4 .extendedReference {
  background: #fff;
}

#part-4 .extendedReference:hover {
  background: white;
  color: teal;
  box-shadow: 2px 4px 20px rgba(0, 0, 0, 0.3);
  transition-duration: 0.4s;
}

.button-outline-purple {
  color: #5c46af;
  border: 2px solid #5c46af;
  transition-duration: 0.5s;
}

.button-outline-purple:hover {
  background: #5c46af;
  color: white;
}

.card-footer {
  padding:1rem 1.25rem;
  background-color: 0;
}
</style>

