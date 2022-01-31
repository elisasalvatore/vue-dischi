<template>
    <div class="disco">
        <img :src="disco.poster" class="pointer" alt="immagine album">
        <span class="title pointer">{{disco.title}}</span>
        <span class="author pointer">{{disco.author}}</span>
        <span class="year pointer">{{disco.year}}</span>
    </div>
</template>

<script>
export default {
    name: 'DiscoBox',
    props: {
        disco: Object
    }
}
</script>

<style lang="scss" scoped>
@import '@/style/variables.scss';

.disco {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: $light-black;
    width: 150px;
    height: 300px;
    margin: 10px;
    border-radius: 10px;

    img {
        width: 150px;
        height: 150px;
        padding: 10px;
    }

    .title {
        text-align: center;
        font-size: 18px;
        text-transform: uppercase;
        color: #fff;
        margin-bottom: 20px;
    }

    .author, 
    .year {
        font-weight: 100;
        color: #ccc;
    }
}
</style>