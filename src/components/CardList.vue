<template>
    <section>
        <FilterGenre @selectClicked="selectDone"/>
        <div class="container">
            <div class="card-wrapper">
                <Cards v-for="(card, index) in filteredGenres" :key="index" :details="card"/>   
            </div>
        </div> 
    </section>
</template>
<script>

import axios from 'axios';
import Cards from './Cards.vue';
import FilterGenre from './FilterGenre.vue';
export default {
    name:'CardlList',
    components: {
        Cards,
        FilterGenre
    },
    data: function() {
        return {
            cardArray: [],
            valueSelected: '',
        };
    },
    methods: {
        selectDone: function(value) {
            this.valueSelected = value;
        }
    },
    computed: {
        filteredGenres: function() {
            if(this.valueSelected === '') {
                return this.cardArray;
            }
            const filteredArray = this.cardArray.filter((item) => {
                return item.genre.toLowerCase().includes(this.valueSelected.toLowerCase());
            });
            return filteredArray;
        }
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