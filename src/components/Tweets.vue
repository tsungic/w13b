<template>
    
    <div>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bulma/0.9.1/css/bulma.min.css"/>

        <button :class="{'is-loading': isLoading }" @click="toggleView">Toggle</button>
       

        <div class="card-content">
            <div class="media">
            <div class="media-content">
                <p class="title is-4">Mark Anthony</p>
                <p class="subtitle is-6">@anthnymark</p>
            </div>
            </div>

            <div class="content">
            yes yes yes <a>@timeless</a>.
            <a href="#">#grind</a> <a href="#">#spend</a>
            <br>
            <time datetime="2018-12-12">11:09 PM - 1 Jan 2016</time>
            </div>
        </div>
        
        <div id="tweets" :class="{ 'list-view': listView }">
            <article class="tweet" v-for="(tweet, index) in tweets" :key="index">
                <h4>{{ tweet.author }} </h4>
                <h6>{{ tweet.date }}</h6>
                <p>{{ tweet.text }}</p>
            </article>
        </div>
    </div>  
</template>



<script>

export default {
    name: 'vue-tweets',

    data() {
        return{
            isLoading: false,
            listView: false,
            tweets: [
                {
                    author: 'Trey',
                    date: 'December 12,2020',
                    text: 'Hello world I am  tweet!!!'
                },
                {
                    author: 'Tsungi',
                    date: 'December 2,2020',
                    text: 'YAYYY!!!'
                },
                {
                    author: 'B',
                    date: 'December 12,2020',
                    text: 'You are muted!!'
                },
                
            ]
        }
    },
    methods: {
        toggleView() {

            this.listView = !this.listView
            this.isLoading = true;
        }
    }, 
}



</script>



<style scoped>

    .is-loading { background: rgb(255, 56, 89); }

    #tweets {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 1rem;
        padding: 1rem;
    }

    #tweets.list-view {
        grid-template-columns: 1fr;
    }

    article {
        padding: 1rem;
        margin: 1rem;
        background-color: pink;
    }
</style>