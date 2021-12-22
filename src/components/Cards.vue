<template>
    <div class="cards">
        <div class="cards-image">
            <img :src="details.poster" :alt="details.title">
        </div>
        <div class="cards-title">
            {{details.title}}
        </div>
        <div class="cards-author">
            {{details.author}}
        </div>
        <div class="cards-year">
           {{details.year}}
        </div>
    </div>
</template>

<script>

export default {
    name:'Cards',
    props: {
        details: Object
    }
}
</script>

<style scoped lang="scss">


.cards {
    max-width: 120px;
    text-align: center;
    width: calc( 100% / 5 );
    padding: 10px;
    margin: 20px;
    background-color: #2e3a46;

    &-title {
        font-size: 15px;
        color: white;
        text-transform: uppercase;
        padding: 10px 0;
    }
    &-author {
        font-size: 12px;
        color: #a19486;
    }
    &-year {
        font-size: 12px;
        color: #a19486;
    }
}

</style>