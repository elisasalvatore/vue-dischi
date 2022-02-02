<template>
    <div class="genre-selected">
        <select v-model="selectGenre" @change="$emit('filter', selectGenre)">
            <!-- 'filter' è il nome CUSTOM dell'evento -->
            <option disabled value="">Musical Genre</option>
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>

    </div>
</template>

<script>
export default {
    data() {
        return {
            selectGenre: '',
        }
    },
}
</script>

<style lang="scss" scoped>
.genre-selected {
    display: flex;
    justify-content: end;
    align-items: center;
    margin: 20px;

    select {
        width: 120px;
        border: none;
        border-radius: 8px;
        padding: 5px;
    }
}
</style>