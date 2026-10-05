<script>
export default {
    name: 'ComicsCard',
    props: {
        image: String,
        title: String
    }
}
</script>

<template>
    <div class="comics-card">
        <img :src="image" :alt="title">
        <h2>{{ title }}</h2>
    </div>
</template>

<style scoped>
.comics-card {
    padding: 0 10px 30px;
}

.comics-card img {
    width: 100%;
    aspect-ratio: 1;
    object-fit: cover;
    object-position: top;
}

.comics-card h2 {
    margin-top: 10px;
    font-size: 0.9rem;
    font-weight: 400;
    text-transform: uppercase;
}
</style> 