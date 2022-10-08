<template>
  <Navbar />
  <section class="home">

    <div class="image">
        <img src="images/profile.png" alt="">
    </div>

    <div class="content">
        <h3>hi, i am {{name}}</h3>
        <span>{{motto}}</span>
        <p>{{content}}</p>
        <a href="about.html" class="btn"> about me <i class="fas fa-user"></i> </a>
    </div>

</section>
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
  data() {
    return {
      name: 'Suwaphat Sriwiset',
      motto: 'If You Don*t Try, How Will You Know',
      content: 'Studied At Bangkok University. Multimedia And Entertainment Engineering Year2'
    }
  }

}
</script>

<style>

</style>