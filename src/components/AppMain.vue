<script>
import ComicsCard from './ComicsCard.vue';
import digitalComics from '../assets/img/buy-comics-digital-comics.png';
import merchandise from '../assets/img/buy-comics-merchandise.png';
import subscriptions from '../assets/img/buy-comics-subscriptions.png';
import shopLocator from '../assets/img/buy-comics-shop-locator.png';
import powerVisa from '../assets/img/buy-dc-power-visa.svg';

export default {
    name: 'AppMain',
    props: {
        comics: Array
    },
    components: { ComicsCard },
    data: () => ({
        buyLinks: [
            { text: 'digital comics', image: digitalComics },
            { text: 'dc merchandise', image: merchandise },
            { text: 'subscription', image: subscriptions },
            { text: 'comic shop locator', image: shopLocator },
            { text: 'dc power visa', image: powerVisa },
        ]
    })
}
</script>

<template>
    <main>
        <section class="jumbotron"></section>
        <section id="comics-list" class="upper-content">
            <div class="container">
                <h1 class="current-series">current series</h1>
                <div class="card-container">
                    <ComicsCard v-for="comic in comics" :key="comic.series" :image="comic.thumb" :title="comic.series" />
                </div>
                <div class="text-center">
                    <button class="load-more">load more</button>
                </div>
            </div>
        </section>
        <section class="lower-content">
            <div class="container">
                <ul>
                    <li v-for="link in buyLinks" :key="link.text">
                        <a href="#">
                            <img :src="link.image" :alt="link.text">{{ link.text }}
                        </a>
                    </li>
                </ul>
            </div>
        </section>
    </main>
</template>

<style scoped>
main {
    color: #fff;
}

.jumbotron {
    height: 400px;
    background-image: url('../assets/img/jumbotron.jpg');
    background-size: cover;
    background-position: top;
}

.upper-content {
    background-color: #1C1C1C;
    padding: 0 0 1.5rem;
}

.upper-content .container {
    position: relative;
}

.current-series {
    position: absolute;
    top: 0;
    left: 10px;
    transform: translateY(-50%);

    background-color: #0282F9;
    padding: 0.5rem 1.5rem;
    font-size: 1.5rem;
    text-transform: uppercase;
}

.text-center {
    text-align: center;
}

.load-more {
    text-transform: uppercase;
    font-size: 0.9rem;
    font-weight: 600;
    padding: 0.6rem 3rem;
    border: none;
    background-color: #0282F9;
    color: #fff;
    cursor: pointer;
}

.lower-content {
    background-color: #0282F9;
    padding: 3rem 0;
}

.lower-content ul {
    display: flex;
    justify-content: space-between;
    list-style: none;
}

.lower-content ul li a {
    text-transform: uppercase;
    font-weight: 300;
    font-size: 16px;
    color: #fff;
    display: flex;
    align-items: center;
    margin: 1rem;
}

.lower-content ul li img {
    margin: 0 .5rem 0 0;
    height: 50px;
    width: auto;
}

.card-container {
    display: flex;
    flex-wrap: wrap;
    padding-top: 4rem;
}

.card-container .comics-card {
    flex-basis: calc(100% / 6);
}
</style>