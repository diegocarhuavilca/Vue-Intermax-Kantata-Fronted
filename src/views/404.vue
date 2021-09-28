<template>
    <div>
        <div class="container-fluid principal">
            <h1>404</h1>
            <h3>Not Found</h3>

            <a href="/">
                <button type="button" class="btn btn-primary">Home</button>
            </a>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.principal {
    display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
    justify-content: center;
    height: 45vh;

    h1 {
        font-size: 5rem;
        font-weight: bold;
    }

    h3 {
        font-size: 3rem;
    }

    .btn-primary {
        background-color: rgb(0, 182, 220);
        border: none;
    }
}
</style>