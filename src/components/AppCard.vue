<script>
import { info } from 'sass';


    export default{
        name : 'AppCard',

        props : {
        CardInfo : Object,
    }
    }

</script>

<template>
    <div class="card">
        <div class="img-container">
            <img v-for="img in CardInfo.card_images" :src="img.image_url" alt="">
        </div>
        <h2 class="card-name">{{ CardInfo.name }}</h2>
        <h2 class="card-type">{{ CardInfo.archetype }}</h2>
        <pre>{{ info }}</pre>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss' as *;
@use '../styles/partials/variables' as *;
@use '../styles/partials/mixins' as *;


.cards{
    min-height: 100px;
    background-color: $primary_color;
    width: calc(100% / 5 - 20px);
    margin-bottom: 30px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    background-color: blue;

    .img-container{
        width: 100%;
        min-height: 20px;
        background-color: red;
    }

    .card-name{
        color: white;
    }

    
}

</style>