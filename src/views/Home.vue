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
                        <router-link to="/contacto">
                            <button
                                type="button"
                                class="btn btn-lg px-4 me-md-2"
                                style="background-color:#00b6dc;color :white"
                            >{{banner_principal.boton.texto}}</button>
                        </router-link>
                    </div>
                </div>
            </div>
        </div>

        <!--BANNER KEY BENEFITS-->

        <div class="container key-benefits px-4 py-5 d-flex" v-if="banner_beneficios">
            <div class="col-md-6 p-3">
                <div
                    class="h-100 p-5 bg-light rounded-3 d-flex flex-column"
                    style="background-color:#00b6dc;"
                >
                    <h2
                        class="fw-bold"
                        style="margin-bottom:1rem"
                    >{{banner_beneficios.tituloIzquierda}}</h2>
                    <p
                        class="lead text-left"
                        style="text-align:left"
                        v-html="banner_beneficios.beneficios"
                    ></p>
                </div>
            </div>
            <div class="col-md-6 p-3">
                <div
                    class="h-100 p-5 bg-light rounded-3 d-flex flex-column justify-content-center align-items-center"
                >
                    <h2 class="fw-bold">Equipos para Carga Dinámica</h2>
                    <p class="lead text-left" style="text-align:justify">
                        El generador PSA opera en Ciclos.
                        <br />Cada recipiente presuriza y despresuriza en menos de 5 segundos.
                        <br />La válvula de ahorro de energía reduce la compresión del uso de aire durante la cobertura.
                    </p>
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
                    <p class="lead" style="text-align:justify" v-html="banner_iso.contenido"></p>
                </div>
            </div>
        </div>

        <!-- INFORMACION FEATURETTES
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

            /END THE FEATURETTES 
            </div>
        </div>-->

        <div class="container px-4 py-5 d-flex flex-column pregunta">
            <h1 style="font-weight:bold;">¿Qué es el oxígeno PSA?</h1>
            <div class="container w-100 d-flex">
                <div class="container w-50">
                    <br />
                    <p
                        class="lead"
                        style="text-align:justify"
                    >PSA es la abreviatura de pressure swing adsorption (adsorción por oscilación de presión).</p>
                    <ul style="list-style:none" class="m-0 p-0">
                        <li>
                            <h2 style="font-weight:bold;text-align:left">Presión</h2>
                            <p
                                class="lead"
                                style="text-align:left"
                            >Se necesitan presiones elevadas para el proceso, generalmente 4-8 bar (g). En caso de que se requiera una presión más alta para su proceso, esta también se puede aplicar.</p>
                        </li>
                        <li>
                            <h2 style="font-weight:bold;text-align:left">Swing</h2>
                            <p
                                class="lead"
                                style="text-align:left"
                            >Mientras se presuriza un recipiente, se despresuriza el otro recipiente.</p>
                        </li>
                        <li>
                            <h2 style="font-weight:bold;text-align:left">Adsorción</h2>
                            <p
                                class="lead"
                                style="text-align:left"
                            >La separación del aire atmosférico se realiza con el principio PSA; el oxígeno se separa del aire mediante un proceso de adsorción.</p>
                        </li>
                    </ul>
                </div>
                <div class="container w-50 d-flex justify-content-center align-items-center">
                    <img
                        src="https://www2.kantata.pe/uploads/Microsoft_Teams_image_9_08e431d8b7.png"
                        class="img-fluid"
                        style="margin-top:2rem"
                        alt
                    />
                </div>
            </div>
        </div>

        <div class="container px-4 py-5">
            <div class="container">
                <div class="container">
                    <h1 style="font-weight:bold;">¿Cómo funciona?</h1>
                    <br />
                    <p class="lead" style="text-align:justify">
                        Las plantas de oxígeno PSA de
                        <strong>KANTATA</strong> se basan en la conocida tecnología PSA (adsorción por oscilación de presión), donde dos recipientes presurizados con zeolita garantizan una producción continua para la separación del oxígeno de otros gases.
                    </p>
                    <p class="lead" style="text-align:justify">
                        El generador de oxígeno
                        <strong>PSA MXA-10</strong> consta de dos recipientes a presión que almacenan zeolita.
                    </p>

                    <div class="container-fluid">
                        <img src="@/assets/Oxygen.png" style="width:75%" alt />
                    </div>
                    <br />
                    <p
                        class="lead"
                        style="text-align:justify"
                    >Se sopla aire comprimido seco a través de una válvula hasta el primer recipiente donde se acumula la presión para alcanzar de 4 a 8 bar. El gas no deseado (Nitrógeno) es adsorbido por la zeolita durante la formación de presión y el oxígeno pasará al tanque de acumulación.</p>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >Mientras la presión aumenta en un recipiente, el otro recipiente se regenera a través de una disminución de la presión. Este proceso garantiza un flujo continuo. Antes de la siguiente etapa de adsorción o desorción, se igualará la presión entre los recipientes de adsorción. Cuando la presión disminuye en el primer recipiente y la zeolita se satura, el producto residual se expulsa a través del sistema de escape. Ahora la presión en el segundo recipiente se acumulará hasta que la presión entre ambos recipientes se iguale una vez más.</p>
                </div>
            </div>
        </div>

        <div class="container px-4 py-5">
            <div class="container">
                <div class="container">
                    <h1 style="font-weight:bold;">Ventajas del PSA</h1>
                    <br />
                    <p class="lead" style="text-align:justify">
                        El proceso de la tecnología PSA (Absorción por oscilación de presión) es una operación extremadamente limpia. El aire es la única “materia prima”.
                        Con un generador de oxígeno
                        <strong>PSA MXA-10</strong> , se garantiza un suministro ininterrumpido de oxígeno.
                    </p>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >Esto significa que puede producir oxígeno en el lugar y el momento que elija, y en la cantidad y calidad que prefiera. Ya no tendrá que esperar a proveedores externos ni pagar precios excesivos por su O2.</p>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >El PSA es un proceso rentable para producir O2. Ofrece el mejor precio de oxígeno industrial para su aplicación.</p>
                    <p class="lead" style="text-align:justify">
                        El proceso de PSA se repite continuamente para proporcionarle un suministro ininterrumpido de oxígeno.
                        Nuestros generadores de oxígeno PSA pueden producir purezas entre el 92 y 95% de oxígeno.
                    </p>
                </div>
            </div>
        </div>

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
                    >Compresor de Alta Presión BST MXA-10</h1>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >Los compresores de Alta Presión BST MXA-10 están diseñados para operar en las aplicaciones industriales, médicas y energéticas. Estos compresores están diseñados para una entrega segura y confiable de oxígeno de alta presión, así como otros gases limpios y secos. El BST MXA-10 es la opción preferida por la industria para aplicaciones de llenado de cilindros de alta presión industriales y médicas.</p>
                    <div class="d-grid gap-2 d-flex justify-content-center">
                        <router-link to="/contacto">
                            <button
                                type="button"
                                class="btn btn-lg px-4 me-md-2"
                                style="background-color:#00b6dc;color :white"
                            >{{banner_principal.boton.texto}}</button>
                        </router-link>
                    </div>
                </div>
            </div>
        </div>

        <div class="container px-4 py-5">
            <div class="container">
                <div class="container">
                    <h1 style="font-weight:bold;">Principio de Funcionamiento</h1>
                    <br />
                    <p
                        class="lead"
                        style="text-align:justify"
                    >El BST MXA-10 cumple la función de elevar la presión del oxígeno que sale del generador a 14 psi, hasta una presión máxima de 200 bar, regulables. Tiene un control de fin de llenado del tanque de salida de oxígeno.</p>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >El sistema se compone de motor principal, instrumentos y elementos de control eléctrico. El funcionamiento del compresor es a través del motor y de la transmisión por correa en V, que impulsa la rotación del cigüeñal, a través de la biela para hacer que el pistón se mueva alternativamente, lo que hace que el volumen del cilindro cambie, conduzca a el oxígeno al cilindro, y luego a través de la válvula de escape, válvula de retención y tubería en el tanque de compensación.</p>
                    <p
                        class="lead"
                        style="text-align:justify"
                    >Los Componentes no necesitan aceite lubricante, así evitamos contaminar el oxígeno presurizado y está formado por una estructura completamente sellada, sin fugas. El rodamiento contiene grasa especial importada, garantizando la durabilidad.</p>
                </div>
            </div>
        </div>

        <!-- APLICACIONES DE GENERADOR DE OXIGENO -->
        <div class="container px-4 py-5">
            <h1
                class="fw-bold lh-1 mb-3"
                style="color:rgba(0,48,110,255);"
            >Aplicaciones del Oxígeno en Diversas Industrias</h1>

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
                                        class="image-cover"
                                        :src="'https://www2.kantata.pe'+app.imagen.url"
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
        <router-link to="/">
            <button type="button" class="btn btn-primary">Home</button>
        </router-link>
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
            const response = await axios.get("https://www2.kantata.pe/home");
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

<style lang="scss" scoped>
.image-cover {
    width: 25vw;
}
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

    .image-cover {
        width: 50vw;
    }

    .pregunta {
        .container {
            display: flex;
            flex-direction: column;

            .container {
                width: 100% !important;
            }
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
                img {
                    width: 50%;
                }
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