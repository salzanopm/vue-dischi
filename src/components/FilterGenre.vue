<template>
    <div class="filter-genre">
        <select @change="miaFunzione" v-model="selectValue" name="" id="select-genre">
            <option value="all">all</option>
            <option value="Rock">Rock</option>
            <option value="Jazz">Jazz</option>
            <option value="Pop">Pop</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "FilterGenre",
    data: function() {
        return {
            selectValue:''
        };
    },
    methods: {
        miaFunzione: function() {
            alert(this.selectValue)
        }
    }
}
</script>

<style scoped>
.filter-genre {
    width: 100%;
    text-align: center;
    padding: 10px 0;
    color: white;
}
#select-genre {
    padding: 10px;
}
</style>