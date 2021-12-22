<template>
    <section>
        <div class="container">
            <div class="card-wrapper">
                <Cards v-for="(card, index) in cardArray" :key="index" :details="card"/>
                
            </div>
        </div> 
    </section>
</template>
<script>

import axios from 'axios';
import Cards from './Cards.vue';
export default {
    name:'CardlList',
    components: {
        Cards
    },
    data: function() {
        return {
            cardArray: [],
        };
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) =>{
            this.cardArray = response.data.response;
        });
    }
}
</script>

<style scoped lang="scss">
    img {
        height: 100%;
        
    }

    section {
        height: 100%;
        background-color: #1e2d3b;
    }

    .card-wrapper {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
</style>