<template>
    <card-component
        :img="require('./assets/imageEquilibrium.jpg')"
        altImg="Image of an Equilibrium"
        title="Equilibrium #3429"
        description="Our
    Equilibrium collection promotes balance and calm"
        :value="0.041"
        currency="ETH"
        :time="3"
        creator="Jules Wyvern"
        creatorLink="https://dellaquila.dev"
        :avatar="require('./assets/imageAvatar.png')"
        avatarAlt="avatar of the creator"
        :viewImg="require('./assets/iconView.svg')"
        viewAlt="View icon"
    />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import CardComponent from './components/CardComponent.vue'

export default defineComponent({
    name: 'App',

    components: {
        'card-component': CardComponent,
    },

    created() {
        return (document.title = '#01 - NFT Card Component')
    },
})
</script>

<style lang="scss">
@import './css/reset.scss';
@import './css/theme.scss';

html,
body,
#app {
    height: 100%;
}

#app {
    background-color: $color-main-bg;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
