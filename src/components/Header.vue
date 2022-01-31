<template>
    <header>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/768px-Spotify_logo_without_text.svg.png" alt="">
    </header>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
@import '@/style/variables.scss';

header {
    height: 80px;
    display: flex;
    align-items: center;
    background-color: $light-black;
    padding-left: 30px;

    img {
        width: 50px;
        height: 50px;
    }
}
</style>