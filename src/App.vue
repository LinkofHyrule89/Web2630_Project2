<template>
    <div class="container">
        <!--ToDo: Use the Header component selector-->
        <appHeader>
            <!--Bind data props quoteCount and set it equal to the quote length-->
            {{quoteCount}}
            <!--Bind data props maxQuotes and set it equal to the maxQuotes created below-->
            {{maxQuotes}}
        </appHeader>


        <!--ToDo: Use the NewQuote component selector-->
        <appNewQuote v-on:click="quoteAdd = newQuote">
            <!--Initiate an $emit event listener called quoteAdded that is equal to newQuote-->
            
        </appNewQuote>

        <!--ToDo: Use the QuoteGrid component selector-->
        <appQuoteGrid>
            <!--Bind data props quotes and set it equal to the quotes array created below-->
            <!--Call quoteDeleted that is emitted from the QuoteGrid Component and pass the deleteQuote method created below-->
        </appQuoteGrid>

        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
//  Todo: Import QuoteGrid, NewQuote, and Header Components
    import Header from './components/Header.vue';
    import NewQuote from './components/NewQuote.vue';
    import Quote from './components/Quote.vue';
    import QuoteGrid from './components/QuoteGrid.vue';

    export default {
        data: function () {
            return {
                // ToDo: Create an array data object called quotes
                    // Have at least one string quote by default
                    quotes: ["This is a quote"],
                    
                // ToDo: Create a data object maxQuotes that is set to 10
                    maxQuotes: 10
            }
        },
        methods: {
            // ToDo: Create a method that checks when a newQuote is created and takes the parameter quote.
                // This method will check if the quotes (Array Data Object) length is greater than or equal to the max quotes allowed
                // If it is return an alert telling the user to delete a quote
                // Outside of conditional, push quote (method parameter) to the quotes array


            // ToDo: Create a method deleteQuote that takes in a parameter of index
                // This method will splice the quotes array by (index, 1)
                deleteQuote: function(index)
                {
                    this.items.splice(index, 1);
                }
        },
        components: {
            // ToDo: Initiate the QuoteGrid, NewQuote, and Header Components with Custom Selectors
            appHeader: Header,
            appNewQuote: NewQuote,
            appQuote: Quote,
            appQuoteGrid: QuoteGrid
        }
        
    }
</script>

<style>
</style>
