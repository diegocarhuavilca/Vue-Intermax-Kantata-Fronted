<template>
    <div v-if="ready">
        <!--BANNER PRINCIPAL-->
        <div class="container banner_principal col-xxl-8 px-4 py-5" v-if="banner_principal">
            <div class="row d-flex align-items-center g-5 py-5">
                <div class="container w-50">
                    <img
                        :src="'https://www2.kantata.pe'+banner_principal.imagen.url"
                        class="d-block mx-lg-auto img-fluid"
                        alt="Generador de Oxigeno"
                        width="300"
                        loading="lazy"
                    />
                </div>
                <div class="container w-50">
                    <h1
                        class="display-5 fw-bold lh-1 mb-3"
                        style="color:rgba(0,48,110,255);"
                    >{{banner_principal.titulo}}</h1>
                    <p class="lead" style="text-align:justify">{{banner_principal.contenido}}</p>
                    <div class="d-grid gap-2 d-flex justify-content-center">
                        <button
                            type="button"
                            class="btn btn-lg px-4 me-md-2"
                            style="background-color:#00b6dc;color :white"
                        >{{banner_principal.boton.texto}}</button>
                    </div>
                </div>
            </div>
        </div>

        <!--INFORMACION CON IMAGENES -->

        <div class="container px-4 py-5" id="custom-cards" v-if="banner_informacion">
            <h1
                class="display-5 fw-bold lh-1 mb-3"
                style="color:rgba(0,48,110,255);"
            >{{banner_informacion.titulo}}</h1>

            <div class="container px-4 py-5" id="featured-3">
                <div class="row g-4 py-5 row-cols-1 row-cols-lg-3">
                    <div class="feature col" v-for="card in banner_informacion.card" :key="card">
                        <div class="feature-icon bg-gradient">
                            <img
                                :src="'https://www2.kantata.pe'+card.imagen.url"
                                width="250"
                                height="250"
                                loading="lazy"
                                alt="Imagen de informacion"
                            />
                        </div>
                        <h4 class="pt-5 mb-4 lh-1 fw-bold">{{card.titulo}}</h4>
                    </div>
                </div>
            </div>
        </div>

        <!--BANNER KEY BENEFITS-->

        <div class="container key-benefits px-4 py-5 d-flex" v-if="banner_beneficios">
            <div class="col-md-6 p-3">
                <div
                    class="h-100 p-5 text-white rounded-3 d-flex flex-column justify-content-center align-items-center"
                    style="background-color:#00b6dc;"
                >
                    <h2 class="fw-bold">{{banner_beneficios.tituloIzquierda}}</h2>
                    <p v-html="banner_beneficios.beneficios"></p>
                </div>
            </div>
            <div class="col-md-6 p-3">
                <div
                    class="h-100 p-5 bg-light rounded-3 d-flex justify-content-center align-items-center"
                >
                    <h2
                        style="color:rgba(0,48,110,255); font-weight:bold"
                    >{{banner_beneficios.tituloPrincipal}}</h2>
                </div>
            </div>
        </div>

        <!--INFORMACION DEL BANNER ISO -->

        <div class="container col-xxl-8 px-4 py-5" v-if="banner_iso">
            <div class="row flex-lg-row-reverse align-items-center justify-content-center g-5 py-5">
                <div class="col-10 col-sm-8 col-lg-6">
                    <img
                        :src="'https://www2.kantata.pe'+ banner_iso.imagen.url"
                        class="d-block mx-lg-auto img-fluid"
                        alt="Imagen certificacion ISO"
                        width="350"
                        loading="lazy"
                    />
                </div>
                <div class="col-lg-6 d-flex flex-column justify-content-center align-items-center">
                    <h1
                        class="display-5 fw-bold lh-1 mb-3"
                        style="color:rgba(0,48,110,255);"
                    >{{banner_iso.titulo}}</h1>
                    <p class="lead">{{banner_iso.contenido}}</p>
                    <div class="d-grid gap-2 d-md-flex justify-content-md-start"></div>
                </div>
            </div>
        </div>

        <!-- INFORMACION FEATURETTES-->
        <div
            class="container-fluid d-flex flex-column justify-content-center"
            v-if="banner_informacion_adicional"
        >
            <div class="container marketing">
                <div
                    class="row featurette"
                    :class="(index%2!=0?'flex-row-reverse':'')"
                    v-for="(card,index) in banner_informacion_adicional.Card"
                    :key="index"
                >
                    <div class="col-md-7 order-md-2 d-flex flex-column justify-content-center">
                        <h2
                            class="featurette-heading fw-bold"
                            style="color:rgba(0,48,110,255);"
                        >{{card.titulo}}</h2>
                    </div>
                    <div class="col-md-5 order-md-1">
                        <img
                            :src="'https://www2.kantata.pe'+card.imagen.url"
                            alt="Imagen caracteristicas"
                            style="width:70%"
                            loading="lazy"
                        />
                    </div>
                </div>

                <!-- /END THE FEATURETTES -->
            </div>
        </div>

        <!-- APLICACIONES DE GENERADOR DE OXIGENO -->
        <div class="container px-4 py-5">
            <h1
                class="fw-bold lh-1 mb-3"
                style="color:rgba(0,48,110,255);"
            >Aplicaciones del generador de gas oxígeno</h1>

            <div class="container">
                <div class="row row-cols-2 grid">
                    <div
                        class="col p-4 d-flex align-content-center"
                        v-for="app in app_data"
                        :key="app._id"
                    >
                        <div class="container-fluid">
                            <div class="image-hover-text-container">
                                <div class="image-hover-image">
                                    <img
                                        v-if="app.imagen.url"
                                        width="400"
                                        :src="'https://kantata-backend.herokuapp.com'+app.imagen.url"
                                    />
                                </div>
                                <h2 class="titulo fw-bold lh-1 mb-3">{{app.titulo}}</h2>
                                <div class="image-hover-text">
                                    <div
                                        class="image-hover-text-bubble d-flex justify-content-center align-items-center"
                                        style="color:white"
                                    >
                                        <div class="container-fluid">{{app.texto}}</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
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
export default {
    data() {
        return {
            banner_principal: null,
            banner_informacion: null,
            banner_beneficios: null,
            banner_iso: null,
            banner_adicional: null,
            app_data: null,
            ready: false,
            error: false,
            error_data: null,
        };
    },

    async beforeCreate() {
        try {
            const response = await axios.get(
                "https://kantata-backend.herokuapp.com/home"
            );
            this.banner_principal = response.data.Banner;
            this.banner_informacion = response.data.Banner_Informacion;
            this.banner_beneficios = response.data.Beneficios;
            this.banner_iso = response.data.ISO;
            this.banner_informacion_adicional =
                response.data.InformacionAdicional;
            this.app_data = response.data.Aplicaciones.Aplicacion;
            this.ready = true;
        } catch (e) {
            this.error = true;
            this.error_data = e;
        }
    },
};
</script>

<style lang="scss">
.boton-secundario {
    background-color: rgb(224, 223, 223);
    transition: 0.3s ease-in-out;
    &:hover {
        background-color: rgba(0, 48, 110, 255);
        color: white;
    }
}

.image-hover-text-container {
    position: relative;
    display: inline-block;
    width: auto;
    height: auto;
    transition: all 0.2s linear;
}

.image-hover-image {
    display: block;
}
.image-hover-image img {
    height: 200px;
}

.titulo {
    margin: auto;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    color: white;
}

.image-hover-text {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    margin: 0 auto;
    cursor: default;
    transition: opacity 0.2s linear;
    .image-hover-text-title {
        opacity: 1;
    }
    opacity: 0;
}
.image-hover-text:hover {
    opacity: 1;
}

.image-hover-text-bubble {
    position: relative;
    box-sizing: border-box;
    height: 200px;
    text-align: center;
    background: rgba(0, 48, 110, 255);
    border: none;
    margin: auto auto;
    padding: 2%;
    overflow: hidden;
    text-align: center;
    word-wrap: break-word;
}

.image-hover-text .image-hover-text-title {
    font-size: 25px;
    display: block;
}
@media screen and (max-width: 1000px) {
    .grid {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        align-content: center;

        .col {
            width: 100%;
        }
    }
}

@media screen and (max-width: 770px) {
    .banner_principal {
        .row {
            flex-direction: column;
            padding: 1.5rem;
            padding-top: 0 !important;

            .container {
                width: 100% !important;
                display: flex;
                align-items: center;
                flex-direction: column;
                margin-top: 0;
            }
        }
    }

    .key-benefits {
        display: flex;
        flex-direction: column-reverse;
        padding: 0 !important;
    }

    #custom-cards {
        padding-bottom: 0 !important;

        #featured-3 {
            padding-bottom: 0 !important;
            padding-top: 0 !important;

            .row {
                padding-bottom: 0 !important;
                padding-top: 0 !important;
            }
        }
    }
}
</style>