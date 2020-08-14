<template>
 <div id="app">
  <!-- <p>

    <router-link to="/foo">Go to sFoo</router-link>
    <router-link to="/bar">Go to Bar</router-link>
  </p> -->

  <router-view>

  </router-view>
</div>
</template>

<script>
import axios from 'axios'
// import Home from './views/Home.vue'
export default {
  name: "App",
  
  components: {
    // Home
  },
  mounted() {
    this.fetchApi()
  },
  data: () => ({
    gitApiData : {}
    
  }),
  methods : {
  async fetchApi () {
    await axios.get(`https://api.github.com/users/KalimaPz`)
    .then((res)=>{
      if(res.statusText == "OK" && res.status == 200)
      // console.log(res.statusText)
      // console.log(res.status)
      // console.log(res.data.login)
      this.gitApiData = res.data
    })
    .catch(() => {
      console.log('ERROR')
    }) 
    
  }
  }
};
</script>

<style scoped>

</style>
