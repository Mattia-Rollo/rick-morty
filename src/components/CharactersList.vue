<template>


    <div class="container">
        <div v-if="!loading">

        </div>

        <div class="row" v-if="!loading">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3">
                <div v-for="(item, index) in characters" :key="item.id" class="chararacter">
                    <img :src="" :alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CharactersList',
    props: ['characters', 'loading']
}
</script>

<style lang="scss" scoped>

</style>