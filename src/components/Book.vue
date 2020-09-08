<template>
    <div class="my-card mb-2">
        <img :src="require('@/assets/images/' + image)" class="float-left" alt="" />
        <span>{{ title }}</span>
    </div>
</template>

<script>
export default {
    props: [ 'title', 'image' ]
}
</script>

<style scoped>
    .my-card {
        min-height: 70px;
        padding: 2px;
        box-shadow: 0 2px 8px 0 rgba(0,0,0,0.2);
        transition: 0.3s;
    }
    .my-card > img {
        margin-top:5px;
        width:60px;
        height:60px;
    }

    .my-card > span {
        vertical-align: middle;
        display:inline-block;
        margin: 20px 10px 20px 10px;
    }

</style>