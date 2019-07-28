<template>
   
  
    <v-content>
       <Carousel/>
       <Progress :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
      <FormVue @quoteCreated="newQuote"/>
      <Message />
           
      <QuoteGrid :quotes="quotes" @quoteDeleted="deletequote"/>
    
    </v-content>
</template>
<script>
// import HelloWorld from './components/HelloWorld'
import FormVue from  './FormVue'

import Carousel from './Carousel'
//import Quote from './components/Quote'
import QuoteGrid from './QuoteGrid'

//import Jumbotron from './components/Jumbotron'
import Progress from './Progress'
import Message from './Message'

export default {
 // name: 'App',
  components: {
   // Header,
    FormVue,
   // Footer,
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
