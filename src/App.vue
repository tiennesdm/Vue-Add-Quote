<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Add</span>
        <span class="font-weight-light">Quotes</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/tiennesdm"
        target="_blank"
      >
        <span class="mr-2">tiennesdm</span>
      </v-btn>
    </v-toolbar>
   

    <v-content>
       <Carousel/>
      <FormVue @quoteCreated="newQuote"/>
      <QuoteGrid :quotes="quotes"/>
    
    </v-content>
    <Footer/>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import FormVue from  './components/FormVue'
import Footer from './components/Footer'
import Carousel from './components/Carousel'
//import Quote from './components/Quote'
import QuoteGrid from './components/QuoteGrid'
//import Jumbotron from './components/Jumbotron'

export default {
  name: 'App',
  components: {
    FormVue,
    Footer,
    Carousel,
 //   Quote,
    QuoteGrid
  //  Jumbotron
  },
  data: ()  => {
    return {
      quotes: [
        'Just to see the Quote'
      ],
      maxQuotes:10
      //
    }
  },
  methods:{
    newQuote(quote){
      console.log('quote', quote);
      this.quotes.push(quote);
    }

  }
}
</script>
