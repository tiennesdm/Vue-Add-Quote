<template>
<v-container>
<div class="row">
        <Quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)" >{{ quote }} </Quote>
    </div>
</v-container>
    
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ['quotes'],
        components: {
            Quote
        },
        methods: {
            deleteQuote(index) {
                console.log('dee', index);
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style>

</style>