<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light static-top sticky-lg-top">
        <div class="container">
            <a class="navbar-brand" href="/">
                <img src="@/assets/logo.png" width="100" alt="">
            </a>
            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto">
                    <li>
                        <router-link to="/about">Nosotros</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {};
</script>

<style lang="scss" scope>
    a{
        text-decoration: none;
        color: rgba(0,48,110,255);
        margin: 0.5rem;
        transition: 0.3s ease-in-out;
        font-weight: bold;

        &:hover{
            color : #00b6dc;
        }
    }
</style>