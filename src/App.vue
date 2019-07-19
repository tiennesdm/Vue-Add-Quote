<template>
  <v-app>
   <Header />
   

    <v-content>
       <Carousel/>
       <Progress :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
      <FormVue @quoteCreated="newQuote"/>
      <v-container>
      <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
            </div>
       
      </v-container>
           
      <QuoteGrid :quotes="quotes" @quoteDeleted="deletequote"/>
    
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
import Header from './components/Header'
//import Jumbotron from './components/Jumbotron'
import Progress from './components/Progress'

export default {
  name: 'App',
  components: {
    Header,
    FormVue,
    Footer,
    Carousel,
 //   Quote,
    QuoteGrid,
    Progress
  //  Jumbotron
  },
  data: ()  => {
    return {
      quotes: [
        'Just to see the Quote'
      ],
      maxQuotes:12
      //
    }
  },
  methods:{
    newQuote(quote){
      if(this.quotes.length===this.maxQuotes){
        alert('Please delete quote first');
      }
      else if(quote === ''){
        alert('Please insert some text');
      }
      else{
         console.log('quote', quote);
      this.quotes.push(quote);

      }
     
    },
    deletequote(index){
      console.log('index', index);
      this.quotes.splice(index, 1);
    }

  }
}
</script>
