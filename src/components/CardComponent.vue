<template>
    <div class="card">
        <a class="image" href="#">
            <img class="thumbnail" :src="img" :alt="altImg" />
            <div class="overlay">
                <img class="icon" :src="viewImg" :alt="viewAlt" />
            </div>
        </a>

        <div class="descriptions">
            <a href="#">
                <h1>{{ title }}</h1></a
            >
            <p>{{ description }}</p>
        </div>
        <div class="price-deadline">
            <span class="currency"
                >{{ value }}
                <p>{{ currency }}</p></span
            >
            <span class="time"
                >{{ time }}
                <p>days left</p>
            </span>
        </div>
        <div class="creator">
            <img :src="avatar" :alt="avatarAlt" />
            <span>
                Creation of
                <a :href="creatorLink" target="_blank">{{ creator }}</a></span
            >
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'CardComponent',
    props: {
        img: String,
        altImg: String,
        title: String,
        description: String,
        value: Number,
        currency: String,
        time: Number,
        timeRemaining: String,
        creator: String,
        creatorLink: String,
        avatar: String,
        avatarAlt: String,
        viewImg: String,
        viewAlt: String,
    },
})
</script>

<style scoped lang="scss">
@import '../css/theme.scss';

.card {
    background-color: $color-card-bg;
    -webkit-box-shadow: 12px 13px 20px 1px rgba(7, 13, 23, 0.89);
    box-shadow: 12px 13px 20px 1px rgba(7, 13, 23, 0.89);
    max-width: 350px;
    border-radius: 12px;
    padding: 25px;

    .image {
        position: relative;
        display: block;

        &:hover {
            .overlay {
                opacity: 0.7;
            }
        }
        .thumbnail {
            width: 100%;
            border-radius: 12px;
            display: block;
        }

        .overlay {
            border-radius: 12px;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            opacity: 0;
            transition: 0.5s ease;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: $color-cyan;
            .icon {
                width: 15%;
            }
        }
    }

    .descriptions {
        h1 {
            font: $font-600;
            color: white;
            margin: 20px 0;
            transition: 0.5s ease;

            &:hover {
                color: $color-cyan;
            }
        }

        p {
            font: $font-400;
            color: $color-soft;
            margin-bottom: 20px;
        }
    }
    .price-deadline {
        display: flex;
        justify-content: space-between;
        padding-bottom: 20px;
        border-bottom: 1px solid $border;
        .currency {
            display: flex;
            color: $color-cyan;
            font: $font-400;
            p {
                margin-left: 5px;
            }
            &::before {
                content: url('../assets/icon-ethereum.svg');
                margin-right: 10px;
                line-height: 29px;
            }
        }

        .time {
            display: flex;
            font: $font-400;
            color: $color-soft;
            p {
                margin-left: 5px;
            }
            &::before {
                content: url('../assets/icon-clock.svg');
                line-height: 29px;
                margin-right: 10px;
            }
        }
    }

    .creator {
        margin: 20px 0;
        font: $font-400;
        color: $color-soft;
        display: flex;
        flex-direction: row;
        align-items: center;

        img {
            border: 1px solid $white;
            border-radius: 20px;
            height: 35px;
            width: 35px;
            margin-right: 10px;
        }

        a {
            color: $white;
            transition: 0.5s ease;
            &:hover {
                color: $color-cyan;
            }
        }
    }
}
</style>
