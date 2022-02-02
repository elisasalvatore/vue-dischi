<template>
    <div class="container">
        <div class="disco">
            <img :src="disco.poster" class="pointer" alt="immagine album">
            <span class="title pointer">{{disco.title}}</span>
            <span class="author pointer">{{disco.author}}</span>
            <span class="year pointer">{{disco.year}}</span>
        </div>
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
.container {

    width: calc(100% / 5 - 20px);
    
    .disco {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: 300px;
        background-color: $light-black;
        margin: 10px;
        padding: 0 10px;
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
    
            &:hover {
                text-decoration: underline;
            }
        }
    
        .author, 
        .year {
            font-weight: 100;
            color: #ccc;
    
            &:hover {
                color: #fff;
            }
        }
    }
}
</style>