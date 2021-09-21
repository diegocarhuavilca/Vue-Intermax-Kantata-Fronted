<template>
    <div v-if="ready">

        <!--BANNER PRINCIPAL-->
        <div class="container banner_principal col-xxl-8 px-4 py-5" v-if="banner_principal">
            <div class="row d-flex align-items-center g-5 py-5">
                <div class="container w-50">
                    <img
                        :src="'http://localhost:1337'+banner_principal.imagen.url"
                        class="d-block mx-lg-auto img-fluid"
                        alt="Bootstrap Themes"
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
                                :src="'http://localhost:1337'+card.imagen.url"
                                width="250"
                                height="250"
                                alt
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
                        :src="'http://localhost:1337'+ banner_iso.imagen.url"
                        class="d-block mx-lg-auto img-fluid"
                        alt="Bootstrap Themes"
                        width="350"
                        loading="lazy"
                    />
                </div>
                <div class="col-lg-6 d-flex flex-column justify-content-center align-items-center">
                    <h1 class="display-5 fw-bold lh-1 mb-3">{{banner_iso.titulo}}</h1>
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
                        <h2 class="featurette-heading fw-bold">{{card.titulo}}</h2>
                    </div>
                    <div class="col-md-5 order-md-1">
                        <img :src="'http://localhost:1337'+card.imagen.url" alt style="width:70%" />
                    </div>
                </div>

                <!-- /END THE FEATURETTES -->
            </div>
        </div>
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
            ready: false,
        };
    },
    async beforeCreate() {
        const response = await axios.get("http://localhost:1337/home");
        this.banner_principal = response.data.Banner;
        this.banner_informacion = response.data.Banner_Informacion;
        this.banner_beneficios = response.data.Beneficios;
        this.banner_iso = response.data.ISO;
        this.banner_informacion_adicional = response.data.InformacionAdicional;
        this.ready = true;
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

@media screen and (max-width: 770px) {
    .banner_principal {

        .row{
            flex-direction: column;
            padding: 1.5rem;
            padding-top: 0 !important;

            .container {
                width:100% !important;
                display:flex;
                align-items: center;
                flex-direction: column;
                margin-top: 0;
            }
        }
    }

    .key-benefits{
        display:flex;
        flex-direction: column-reverse;
        padding: 0 !important;
    }

    #custom-cards{
        padding-bottom: 0 !important;

        #featured-3{
            padding-bottom: 0 !important;
            padding-top: 0 !important;

            .row{
                padding-bottom: 0 !important;
                padding-top: 0 !important;
            }
        }


    }
}
</style>