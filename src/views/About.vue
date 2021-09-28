<template>
    <div class="about" v-if="ready">
        <div class="px-4 banner-inicial py-5 my-5 text-center">
            <img class="d-block mx-auto mb-4" src="@/assets/logo-square.png" alt width="72" />
            <h1 class="display-5 fw-bold">{{data_About.Banner.titulo}}</h1>
            <div class="col-lg-6 mx-auto">
                <p class="lead mb-4">{{data_About.Banner.contenido}}</p>
                <div class="d-grid gap-2 d-sm-flex justify-content-sm-center"></div>
            </div>
        </div>

        <div class="container mision-vision px-4 py-5">
            <div class="container-fluid d-flex">
                <div class="container w-50 col">
                    <h2 style="font-weight: bold">Mision</h2>
                    <p>{{data_About.MisionVision.mision}}</p>
                </div>
                <div class="container w-50 col">
                    <h2 style="font-weight: bold">Vision</h2>
                    <p>{{data_About.MisionVision.vision}}</p>
                </div>
            </div>
        </div>

        <!-- <div class="container-fluid p-5">
            <carousel :items-to-show="1" :wrap-around="true" :breakpoints="breakpoints">
                <slide v-for="slide in data_About.Carousel" :key="slide">
                    <img
                        :src="'https://kantata-backend.herokuapp.com'+slide.url"
                        alt
                        class="img-fluid"
                    />
                </slide>

                <template #addons>
                    <navigation />
                </template>
            </carousel>
        </div>-->

        <div class="container px-4 py-5 certificaciones">
            <div class="container-fluid d-flex">
                <div
                    class="container w-50 col"
                    v-for="(certi,index) in data_About.certificacion"
                    :key="index"
                >
                    <img
                        v-if="certi.imagen"
                        :src="'https://kantata-backend.herokuapp.com'+certi.imagen.url"
                        class="my-5"
                        width="200"
                        height="200"
                    />
                    <h2 style="font-weight: bold">{{certi.titulo}}</h2>
                    <p>{{certi.contenido}}</p>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import axios from "axios";
import "vue3-carousel/dist/carousel.css";
// import { Carousel, Slide, Navigation } from "vue3-carousel";
export default {
    name: "App",
    components: {
        // Carousel,
        // Slide,
        // Navigation,
    },
    data() {
        return {
            data_About: null,
            ready: false,
            breakpoints: {
                780: {
                    itemsToShow: 2.5,
                    snapAlign: "center",
                },
            },
        };
    },
    async beforeCreate() {
        const response = await axios.get(
            "https://kantata-backend.herokuapp.com/nosotros"
        );
        this.data_About = response.data;
        this.ready = true;
    },
};
</script>

<style lang="scss" scoped>
@media screen and (max-width: 780px) {
    .banner-inicial {
        margin: 0 !important;
    }
    .mision-vision {
        padding: 0 !important;
        .container-fluid {
            display: flex;
            flex-direction: column;

            .container {
                width: 100% !important;
            }
        }
    }

    .certificaciones {
        padding: 0 !important;
        .container-fluid {
            flex-direction: column;

            .container {
                width: 100% !important;
            }
        }
    }
}
</style>