<script setup lang="ts">
const carousels = [
    { text: "Slide 1", color: "#445e00" },
    { text: "Slide 2", color: "#006724" },
    { text: "Slide 3", color: "#b60000" },
    { text: "Slide 4", color: "#f4c300" },
    { text: "Slide 5", color: "#005c98" },
];
</script>

<template>
    <section>
        <o-carousel indicator-inside>
            <o-carousel-item v-for="(carousel, i) in carousels" :key="i">
                <article
                    class="example-slide"
                    :style="{ 'background-color': carousel.color }">
                    <h1>{{ carousel.text }}</h1>
                </article>
            </o-carousel-item>
        </o-carousel>
    </section>
</template>

<style>
.example-slide {
    padding: 9rem 4.5rem;
    color: #ffffff;
    text-align: center;
}
</style>
