<template>
    <div id="footer">
        <footer class="container">
            <div class="row pt-3">
                <div class="col-md-4 text-primary bold animated bounceInLeft">
                    Developed by Zeljko Lazovic
                </div>
                <div class="col-md-2 offset-md-4 animated flash faster infinite">
                    <div v-if=" $route.path!= 'contact' ">
                        <router-link class="bold" :to="{ name: 'contact' }">
                            hire me
                        </router-link>
                    </div>
                </div>
                <div class="col-md-2 animated bounceInRight">
                    <div class="text-primary bold" style=";">Follow Me</div>
                    <br>
                    <ul>
                        <li v-for="(classIcon,index) in classFontAwesomeIcon" :key="index">
                            <a :href="link[index]">
                                <i :class="classIcon" class="bold"> 
                                </i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
export default {
  data() {
    return {
      classFontAwesomeIcon: ["fab fa-facebook-f", "fab fa-linkedin-in", "fab fa-github"],
      link : ['https://www.facebook.com/zeljko.lazovic.12', 'https://www.linkedin.com/in/zeljko-lazovic/', 'https://github.com/Zeks92']
    };
  }
};
</script>

<style scoped>

#footer{
  box-shadow: 2px 4px 20px rgba(0, 0, 0, 1);
  background: #ebebe0;
  background-attachment: fixed;
  background-position: center;
  bottom: 0;
  position: relative;
}
ul {
  padding: 0;
  display: -webkit-box;
  list-style: none;
}

li {
  margin-right: 15px;
}

i{
    font-size: 20px;
    padding: 6px;
    transition-duration: 1.5s;
}

i:hover{
   color: #000;
   border:2px solid;
   border-radius:50%;
}


a{
    text-decoration: none;
    text-transform: uppercase;
}

.bold {
    font-weight: bold !important;
}



</style>
