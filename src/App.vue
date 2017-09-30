<template>
    <div style="margin-top: 60px;" class="container">
        <app-progress :progress="progress"></app-progress>
        <app-add-quote :progress="progress"></app-add-quote>
        <app-quotes :progress="progress"></app-quotes>
        <div style="margin-top: 60px;" class="row">
            <p style="text-align: center" class="alert alert-info">Info: Click on a quote to delete it!</p>
        </div>
    </div>
</template>

<script>
    import Progress from './components/Progress.vue';
    import AddQuote from './components/AddQuote.vue';
    import Quotes from './components/Quotes.vue';

    export default {
        data: function() {
            return {
                progress: {
                    value: 0
                }
            };
        },
        components: {
            appProgress: Progress,
            appAddQuote: AddQuote,
            appQuotes: Quotes
        }
    }
</script>

<style>
    .quote {
        font-family: Arizonia;
        font-size: 24px;
        
    }

    .inner-quote {
        border: 1px solid #ccc;
        border-radius: 5px;
        margin: 10px;
        padding: 10px;
        cursor: pointer;
    }

    .inner-quote:hover {
        background-color: #5bc0de;
    }
</style>
