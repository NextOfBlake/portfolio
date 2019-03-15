<template>
    <div class="card-list">
        <div class="card" v-for="card in cards">
            <component :is="card.component"/>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['cards']
    }
</script>

<style lang="scss">

</style>