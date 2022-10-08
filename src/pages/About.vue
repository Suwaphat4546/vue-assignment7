<template>
  <Navbar />
  <section class="about">

        <h1 class="heading"> about <span>me</span> </h1>

        <div class="row">

            <div class="info-container">

                <h1>personal info</h1>

                <div class="box-container">

                    <div class="box">
                        <h3> <span>name : </span> {{name}} </h3>
                        <h3> <span>age : </span> {{age}} </h3>
                        <h3> <span>email : </span> {{email}} </h3>
                    </div>

                    <div class="box">
                        <h3> <span>occupation : </span> {{occupation}} </h3>
                        <h3> <span>address : </span> {{address}} </h3>
                        <h3> <span>language : </span> {{language}} </h3>
                    </div>

                </div>

            </div>

        </div>

    </section>

    <!-- about section ends -->

    <!-- skills section starts  -->

        <section class="skills">

            <h1 class="heading"> <span>my</span> skills </h1>

            <div class="box-container">
                <div class="box" v-for="s in skills" :key="s.name">
                    <img :src="s.image">
                    <h3>{{s.name}}</h3>
                </div>
                
            </div>

        </section>

    <!-- skills section ends -->

    <!-- education section starts  -->

    <section class="education">

        <h1 class="heading"> <span>my</span> experience </h1>

        <div class="box-container">

            <div class="box" v-for="e in experiences" :key="e.years">
                <i class="fas fa-briefcase"></i>
                <span>{{e.years}}</span>
                <h3>{{e.company}}</h3>
                <p>{{e.jobs}}</p>
            </div>

        </div>

    </section>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import axios from 'axios'

export default {
  components: { Navbar },
  methods:{
    async fetchExperience() {
        try {
            let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/experiences")
            this.experiences = res.data
        } catch (error) {

        }
    },
    async fetchSkills() {
        try {
            let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/skills")
            this.skills = res.data
        } catch (error) {

        }
    }
  },
  data() {
    return {
      name:'Suwaphat Sriwiset',
      age:'19',
      email:'suwaphat.sriw@bumail.net',
      address:'Pathum Thani, Thailand 12120',
      language:'thai',
      occupation:'student',
      experiences: [],
      skills: []
    }
  },
  beforeMount() {
    this.fetchExperience()
    this.fetchSkills()
  }
}
</script>

<style>

</style>