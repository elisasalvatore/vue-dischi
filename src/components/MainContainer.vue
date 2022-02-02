<template>
    <div class="container-dischi">
        <disco-box
            v-for="(disco,index) in dischi"
            :key="index"
            :disco="disco"
        />

    </div>
</template>

<script>
import DiscoBox from './DiscoBox.vue'

export default {
    components: {
        DiscoBox
    },
    props: {
        dischi: Array
    }
}
</script>

<style lang="scss" scoped>

.container-dischi {
    margin: 0 auto;
    width: 1000px;
    display:flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    padding-top: 20px;
}
</style>