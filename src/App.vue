<template>
  <v-app>
   <Header />
   

    <v-content>
       <Carousel/>
       <Progress :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
      <FormVue @quoteCreated="newQuote"/>
      <Message />
           
      <QuoteGrid :quotes="quotes" @quoteDeleted="deletequote"/>
    
    </v-content>
    <Footer/>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import FormVue from  './components/Main-app/FormVue'
import Footer from './components/Main-app/Footer'
import Carousel from './components/Main-app/Carousel'
//import Quote from './components/Quote'
import QuoteGrid from './components/Main-app/QuoteGrid'
import Header from './components/Main-app/Header'
//import Jumbotron from './components/Jumbotron'
import Progress from './components/Main-app/Progress'
import Message from './components/Main-app/Message'

export default {
  name: 'App',
  components: {
    Header,
    FormVue,
    Footer,
    Carousel,
 //   Quote,
    QuoteGrid,
    Progress,
    Message
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
