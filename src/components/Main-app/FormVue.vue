<template>
<v-container>
       <v-layout align-center>
      <v-flex xs12 sm12 md12>
              <v-card
    class="pa-5"
    color="white"
    flat
  >  
     <v-form>
              <v-textarea
          outline
          name="input-12-8"
          label="Ouote"
          value="" v-model ="quote"
        ></v-textarea>
          <v-btn block color="info" @click.prevent="createQuote">
          Add Quote
        </v-btn>
           </v-form>
            <v-divider class="my-3"></v-divider>
           <h6>{{quote}}</h6>
          </v-card>
        

    </v-flex>
       </v-layout>
  
  
     <!--   <textarea class="form-control" rows="3" v-model="quote"></textarea> -->
      
   


</v-container>

 
        
    
</template>
<script>
export default {
     data: () => {
    return {
      quote: ""
    };
  },
  methods: {
    createQuote() {
      this.$emit("quoteCreated", this.quote);
      this.quote = "";
    }
  }
};
</script>