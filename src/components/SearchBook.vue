<template>
    <div class="px-2 py-4">
        <input type="text" v-model="searchInput" 
            placeholder="Cari Buku" 
            class="form-control" id="">
    </div>
</template>

<script>
export default {
    data() {
        return {
            searchInput: '',
        }
    },
    watch : {
        searchInput() {
            this.$emit('search-input', this.searchInput);
        }
    }
}
</script>

<style scoped>
    div {
        width:100%;
    }

    input[type=text] {
        border:5px solid blue;
        padding-top: 2px;
        padding-bottom: 2px;
    }
</style>