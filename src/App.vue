<template>
 <v-app>
 <!--<Header /> --> 
  <v-content>
  <router-view></router-view>
  </v-content>
  <Footer/>
 </v-app>
</template>

<script>
import Footer from './components/Main-app/Footer'
import Header from './components/Main-app/Header'

export default {
  name: "App",
  components: {
    Header,
    Footer

  }

  
}
</script>
