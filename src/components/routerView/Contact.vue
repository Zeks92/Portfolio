<template>
<section id="wrapping" class="px-3">
    <div class="container text-primary mt-5 px-2">
        <div class="row py-3">
            <div class="col-md-6 d-none d-md-block animated fadeInUpBig">
                <!-- img -->
                <div  id="saturate" class="target-img transitionAnimated">
                    <h4 class="row target-img-text pl-3">
                      <p style="width: 100%; margin-top: 150px;">Let's</p>
                      <p style="width: 100%">Work</p>
                      <p style="width: 100%">Together</p>
                    </h4>
                </div>  
            </div>
            <div class="col-md-6 col-sm-12 animated fadeInDownBig whiteBg">
                <form class="form" role="form" autocomplete="off">
                    <div class="form-group row" v-for="(label, index) in label_array" :key="index">
                        <label class="col-lg-3 col-form-label form-control-label text-purple">{{ label }} :</label>
                        <div class="col-lg-9">
                            <input @focus="saturateRemove" class="form-control" :type="input_type_array[index]" :placeholder="placeholder_text_array[index]" required>
                        </div>
                    </div>
                    <div class="form-group row">
                        <label class="col-lg-3 col-form-label form-control-label text-purple">Message :</label>
                        <div class="col-lg-9">
                            <textarea @focus="saturateRemove" name="Work Requirement - description"></textarea>
                        </div>
                    </div>
                    <div class="form-group row">
                        <label class="col-lg-3 col-form-label form-control-label"></label>
                        <div class="col-lg-9">
                            <input type="button" class="btn btn-block button-outline-green" value="Send" style="color:white">
                            <input @click="saturateAdd" type="reset" class="btn btn-block button-outline-red" value="Cancel">
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</section>
</template>

<script>
export default {
  data: function() {
    return {
      label_array: ["Name", "Last Name", "Email", "Phone", "Subject"],
      input_type_array: ["text", "text", "email", "text", "text"],
      placeholder_text_array: ["Name", "Last Name", "example@mail.com", "", ""]
    };
  },
  methods: {
    saturateRemove() {
      var temp = document.getElementById("saturate");
      temp.classList.add("dynammicsaturate_Remove");
    },
    saturateAdd(){
        var temp = document.getElementById("saturate");
        temp.classList.remove("dynammicsaturate_Remove");
        temp.classList.add("dynammicsaturate_Add");
    }
  }
};
</script>

<style scoped>
#wrapping{
    background-image: linear-gradient(0deg, #009efd 0%, #21d4fd 100%);
}
.target-img {
  background: url("https://images.unsplash.com/photo-1518135714426-c18f5ffb6f4d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=773&q=80");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100%;
  filter: saturate(80%);
}
.dynammicsaturate_Add{
  filter: saturate(80%);
}
.dynammicsaturate_Remove,
.target-img:hover{
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.5);
  filter: saturate(250%);
}
.target-img-text {
  font-size: 50px;
  width: 100%;
  color: #ff0000;
}
.transitionAnimated{
  transition-duration: 0.75s;
}

.whiteBg{
    background-color: #fff;
    padding-top: 50px;
}
.whiteBg:hover {
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.5);
}
.text-purple{
    color: #806dc5;
}
.button-outline-green{
  background: #00ff00;
}
.button-outline-red {
  background: #ff0000;
}
</style>
