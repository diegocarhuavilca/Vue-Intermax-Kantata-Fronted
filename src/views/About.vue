<template>
    <div class="about" v-if="ready">
        <div class="px-4 py-5 my-5 text-center">
            <img class="d-block mx-auto mb-4" src="@/assets/logo-square.png" alt width="72" />
            <h1 class="display-5 fw-bold">{{data_About.Banner.titulo}}</h1>
            <div class="col-lg-6 mx-auto">
                <p
                    class="lead mb-4"
                >{{data_About.Banner.contenido}}</p>
                <div class="d-grid gap-2 d-sm-flex justify-content-sm-center"></div>
            </div>
        </div>

        <div class="container px-4 py-5">
            <div class="container-fluid d-flex">
                <div class="container w-50 col">
                    <h2 style="font-weight: bold">Mision</h2>
                    <p>{{data_About.Banner.MisionVision.mision}}</p>
                </div>
                <div class="container w-50 col">
                    <h2 style="font-weight: bold">Vision</h2>
                    <p>{{data_About.Banner.MisionVision.mision}}</p>
                </div>
            </div>
        </div>

        <div class="container-fluid p-5">
            <carousel :items-to-show="3">
                <slide v-for="slide in 5" :key="slide" class="container">
                    <img src="https://picsum.photos/500/300" alt />
                </slide>

                <template #addons>
                    <navigation />
                </template>
            </carousel>
        </div>

        <div class="container px-4 py-5">
            <div class="container-fluid d-flex">
                <div class="container w-50 col">
                    <img src="https://picsum.photos/150/150" alt class="my-5" />
                    <h2 style="font-weight: bold">Certificacion 1</h2>
                    <p>Paragraph of text beneath the heading to explain the heading. We'll add onto it with another sentence and probably just keep going until we run out of words.</p>
                </div>
                <div class="container w-50 col">
                    <img src="https://picsum.photos/150/150" alt class="my-5" />
                    <h2 style="font-weight: bold">Certificacion 2</h2>
                    <p>Paragraph of text beneath the heading to explain the heading. We'll add onto it with another sentence and probably just keep going until we run out of words.</p>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import axios from 'axios'
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation } from "vue3-carousel";
export default {
    name: "App",
    components: {
        Carousel,
        Slide,
        Navigation,
    },
    data(){
        return{
            data_About : null,
            ready:false,
        }
    },
    async beforeCreate() {
        const response = await axios.get ('http://localhost:1337/nosotros')
        this.data_About = response.data
        this.ready = true
    },
};
</script>