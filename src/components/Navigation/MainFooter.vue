<template>
    <!-- Footer -->
    <footer class="text-center text-lg-start text-muted mt-5" id="footer">
        <!-- Section: Links  -->
        <section class="p-5">
            <div class="container text-center text-md-start mt-5">
                <!-- Grid row -->
                <div class="row mt-3">
                    <!-- Grid column -->
                    <div class="col-md-3 col-lg-4 col-xl-3 mx-auto mb-4">
                        <!-- Content -->
                        <div class="container w-50">
                            <img src="@/assets/logo.png" class="img-fluid" />
                        </div>
                    </div>
                    <!-- Grid column -->
                    <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mb-4">
                        <!-- Links -->
                        <h6
                            class="text-uppercase fw-bold mb-4"
                            style="color:rgba(0,48,110,255)"
                        >Secciones</h6>
                        <p class="m-0">
                            <router-link to="/about" class="text-reset m-0">Sobre Nosotros</router-link>
                        </p>
                        <p class="m-0">
                            <router-link to="/" class="text-reset m-0">Nuestros Productos</router-link>
                        </p>

                        <p class="m-0">
                            <router-link to="/contacto" class="text-reset m-0">Contactenos</router-link>
                        </p>
                    </div>
                    <!-- Grid column -->

                    <!-- Grid column -->
                    <div class="col-md-4 col-lg-3 col-xl-3 mx-auto mb-md-0 mb-4">
                        <!-- Links -->
                        <h6
                            class="text-uppercase fw-bold mb-4"
                            style="color:rgba(0,48,110,255)"
                        >Contacto</h6>
                        <p>
                            <i class="fas fa-envelope fa-lg me-3" style="color:rgba(0,48,110,255);width:25px;"></i>
                            info@kantata.pe
                        </p>
                        <p>
                            <img
                                src="@/assets/spain.png"
                                class="img-fluid"
                                style="margin-right:20px"
                                width="25"
                                alt
                            />+34 936 272 598
                        </p>
                        <p>
                            <img
                                src="@/assets/peru.png"
                                class="img-fluid"
                                width="25"
                                style="margin-right:20px"
                                alt
                            />+511 740 1102
                        </p>
                        <p>
                            <img
                                src="@/assets/united-states.png"
                                class="img-fluid mr-2"
                                style="margin-right:20px"
                                width="25"
                                alt
                            />+ 1786 796 1322
                        </p>
                    </div>
                    <!-- Grid column -->
                </div>
                <!-- Grid row -->
            </div>
        </section>
        <!-- Section: Links  -->

        <!-- Copyright -->
        <div class="text-center p-4" style="background-color: rgba(0,48,110,255); color:white">
            © 2021 Copyright
            Kantata
        </div>
        <!-- Copyright -->
    </footer>
    <!-- Footer -->
</template>

<script>
export default {};
</script>

<style>
</style>
