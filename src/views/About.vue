<template>
    <div class="about" v-if="ready">
        <div class="px-4 banner-inicial py-5 my-5 text-center">
            <img class="d-block mx-auto mb-4" src="@/assets/logo-square.png" alt width="72" />
            <h1 class="display-5 fw-bold">{{data_About.Banner.titulo}}</h1>
            <div class="col-lg-6 mx-auto">
                <p class="lead mb-4 contenido" v-html="data_About.Banner.contenido"></p>
                <div class="d-grid gap-2 d-sm-flex justify-content-sm-center">
                    <br />
                </div>
                <img src="@/assets/mapa.png" class="img-fluid" alt />
                <p class="lead mb-4 contenido">
                    <br />Nuestra sucursal en Miami, atiende a todo el mercado Norteamericano y Centro América. Nuestra oficina de Lima, Perú, está enfocada en atender las necesidades de nuestros clientes en Latinoamérica, y el mercado Europeo lo asistimos a través de nuestra oficina en Barcelona, España.
                    <br />
                    <br />Independientemente de la Solución que escoja y del lugar donde nos contacte, siempre obtendrá la máxima calidad y los costos energéticos más bajos, así como un servicio de mantenimiento preventivo y post venta acorde a sus expectativas.
                </p>
            </div>
        </div>
        <div class="container">
            <div class="row mis">
                <div class="col">
                    <div class="container-fluid col">
                        <h2 style="font-weight: bold">Mision</h2>
                        <p class="lead contenido">{{data_About.MisionVision.mision}}</p>
                    </div>
                </div>
                <div class="col">
                    <div class="container-fluid col">
                        <h2 style="font-weight: bold">Vision</h2>
                        <p class="lead contenido">{{data_About.MisionVision.vision}}</p>
                    </div>
                </div>
            </div>
            <div class="row fila">
                <div class="col d-flex align-items-center">
                    <div class="container-fluid">
                        <img src="@/assets/logo.png" class="img-fluid" alt />
                    </div>
                </div>
                <div class="col d-flex align-items-center">
                    <div class="container px-4 py-5 certificaciones">
                        <div class="container-fluid d-flex">
                            <div
                                class="container w-50 col d-flex flex-column align-items-center"
                                v-for="(certi,index) in data_About.certificacion"
                                :key="index"
                            >
                                <img
                                    v-if="certi.imagen"
                                    :src="'https://www2.kantata.pe'+certi.imagen.url"
                                    class="my-3"
                                    width="200"
                                    alt="Certificaciones"
                                />
                                <h2 style="font-weight: bold">{{certi.titulo}}</h2>
                                <br />
                                <p class="lead w-100 contenido" v-html="certi.contenido"></p>
                            </div>
                        </div>
                    </div>
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
    </div>
    <div
        v-if="(error==false && ready==false)"
        class="container-fluid d-flex justify-content-center"
    >
        <lottie-player
            src="https://assets1.lottiefiles.com/packages/lf20_Z4BhGL.json"
            background="transparent"
            speed="1"
            style="width: 300px; height: 300px;"
            loop
            autoplay
        ></lottie-player>
    </div>
    <div v-if="error">
        <h1>ERROR</h1>
        <h5>{{error_data}}</h5>
        <a href="/">
            <button type="button" class="btn btn-primary">Home</button>
        </a>
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
            error: false,
            error_data: null,
        };
    },
    async beforeCreate() {
        try {
            const response = await axios.get(
                "https://www2.kantata.pe/nosotros"
            );
            this.data_About = response.data;
            this.ready = true;
        } catch (error) {
            this.error = true;
            this.error_data = error;
        }
    },
};
</script>

<style lang="scss" scoped>
.contenido {
    text-align: justify;
}

@media screen and (max-width: 1000px) {
    .fila {
        display: flex;
        flex-direction: column;
    }
}
@media screen and (max-width: 780px) {
    .mis {
        display: flex;
        flex-direction: column;
    }
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