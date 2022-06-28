<template>
    <div class="jogo">

        <Forca></Forca>
        
    </div>
</template>

<script>
import Forca from './Forca.vue'




    export default {
    name: "Jogo",
    props: {},
    data() {
        return {};
    },
    methods: {},
    components: { Forca }
}
</script>

<style>
    .jogo{
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
</style>