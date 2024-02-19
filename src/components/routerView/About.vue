<template>
<section id="wrapper" class="px-3">
    <div class="container pt-5">
        <div class="row">
            <div class="col-md-6 animated fadeInLeft wrapper">
                <div class="row customDesign">
                    <div class="container">
                        <div class="row py-2 heading">
                            Professional Experience
                        </div>
                        <div class="container">
                            <div class="row">
                            <div class="col" id="professionalExp">
                                <div v-for="(professionalExp, index) in professionalExpirience" :key="index">
                                    <div class="row pt-3">
                                        <div class="col-2 offset-8" id="from" style="text-align:right"> {{ professionalExp.from }} </div> -
                                        <div class="col-1" id="to" style="text-align:right"> {{ professionalExp.to }} </div>
                                    </div>
                                    <div class="row">
                                        <div class="col-sm-7" style="margin-top:-22px" id="company_name">
                                            {{ professionalExp.company_name }}
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col" id="profile">
                                            {{ professionalExp.pr_profile }}
                                        </div>
                                    </div>
                                    <div class="row">
                                        <div class="col text-center pt-2" id="work_description">
                                            {{ professionalExp.work_description }}
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="row py-2 heading">
                        faculty
                    </div>
                    <div class="col" id="edfaculty">
                        <div v-for="(edfaculty, index) in Education" :key="index">
                            <div class="row  pt-3">
                                <div class="col-2 offset-8" id="from" style="text-align:right"> {{ edfaculty.from}} </div> -
                                <div class="col-1" id="to" style="text-align:right">{{ edfaculty.to }} </div>
                            </div>
                            <div class="row">
                                <div class="col-sm-7" style="margin-top:-22px" id="faculty_name">
                                    {{ edfaculty.faculty_name }}
                                </div>
                            </div>
                            <div class="row">
                                <div class="col" id="faculty_course">
                                    Course : {{ edfaculty.faculty_course }}
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-6 animated fadeInRight wrapper">
              <div class="row customDesign">
                <div class="container">
                  <div class="row py-2 heading">
                    Personality
                  </div>
                  <div class="row">
                    <div class="col-10 offset-1">
                      <ul style="list-style-type:none">
                        <li v-for="attribute in listAttributes" v-bind:key="attribute.id">{{attribute}}</li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
              <div class="row customDesign">
                <div class="container">
                  <div class="row py-2 heading">
                    Language Skills
                  </div>
                  <div class="row">
                    <div class="col-10 offset-1">
                      <ul class="languages" style="list-style-type:none;width:70%;">
                        <li>English<i class="fas fa-star english"></i></li>
                        <li>German<i class="fas fa-star german"></i></li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
              <div class="row customDesign">
                <div class="container">
                  <div class="row py-2 heading">
                    Hobbies
                  </div>
                  <div class="row py-4">
                    <div class="col-2 offset-1"><i class="fas fa-table-tennis hobbies tabletennis"></i></div>
                    <div class="col-2 offset-1"><i class="fas fa-book hobbies reading"></i></div>
                    <div class="col-2 offset-1"><i class="fas fa-futbol hobbies football"></i></div>
                    <div class="col-2 offset-1"><i class="fas fa-gamepad hobbies games"></i></div>
                  </div>
                </div>
              </div>
            </div>
        </div>
    </div>
</section>
</template>

<script>
export default {
  data: function() {
    return {
      email: "zeks1992@gmail.com",
      number: 649885117,
      professionalExpirience: {
        // you can add several work expirience below
        1: {
          from: '1/9/18',
          to: '8/30/21',
          company_name: "Freelance",
          pr_profile: "Frontend Developer",
          work_description: "Development of new websites and applications using latest tools and technologies in web development"
        },
        2: {
          from: '1/9/21',
          to: 'present',
          company_name: 'AlgoMetric',
          pr_profile: 'Frontend Developer',
          work_description: 'Working on different projects for some of the major clients in tax business'
        }
      },
      Education: {
        1: {
          from: "2012",
          to: "2018", // if still on faculty just enter -> 'present'
          faculty_name: "University John Naisbitt",
          faculty_course: "Information Technology"
        }
        /*
          Add more education here
        */
      },
      listAttributes: ['Hardworking','Creative', 'Communicative', 'Organized', 'Punctuallity', 'Responsible' ]
   
    };
  }
};
</script>

<style scoped>
#wrapper{
    background-image: linear-gradient(180deg, #2af598 0%, #009efd 100%);
    padding-top:5%; 
    padding-bottom:1%;
}
.customDesign{
    padding-bottom: 3%;
    padding-top: 3%;
    border-bottom: 1px solid black !important;
}
.wrapper{
    background: #ffff66; 
    box-shadow: 0px 5px 2px #888888;
     
}

.heading{
   text-decoration: underline;
   text-transform: uppercase;
   justify-content: center;
   margin: auto;
   width: 100%;
   color: teal
}

#from,
#to{
    color: red;
}

#company_name{
    color: blue;
}
li:nth-child(odd),
li:nth-child(even) {
  border:1px solid teal;
  text-align:center;
}
li:nth-child(odd) {
  color: red;
}
li:nth-child(even) {
  color: blue;
}
.languages li {
  margin-left:0px;
  padding-left:0px;
  float:left;
  border:none;
}
.languages li i {
  margin-left: 15px;
}
.languages li i::before {
  font-family: "Font Awesome 5 Free";
}
.languages li i.english::before {
  content:"\f005 \f005 \f005 \f005 \f005";
}
.languages li i.german::before {
  content:"\f005 \f005 \f005";
}
.hobbies {
  font-size:52px;
}

@media(max-width: 768px) {
   .fas {
    font-size:10px;
      }
}


#profile{
    color: royalblue;
}

</style>
