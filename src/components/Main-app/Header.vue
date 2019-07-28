<template>
<v-toolbar>
   <router-link to="/"> 
      <v-toolbar-title class="headline text-uppercase dec">
        <span>Add</span>
        <span class="font-weight-light">Quotes</span>
      </v-toolbar-title>
      </router-link>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/tiennesdm"
        target="_blank"
      >
        <span class="mr-2">tiennesdm</span>
      </v-btn>
   <router-link to="/form">   <v-btn>Form</v-btn></router-link>
    </v-toolbar>
</template>
<script>
export default {
    
}
</script>
<style>
.dec{
  text-decoration: none;
}
  
</style>