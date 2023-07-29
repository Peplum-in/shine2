<template>
    <div>
        <section class="py-0">
            <div class="columns">
                <div class=" column is-6-desktop ">
                    <p class="title ">
                       Our Clients
                    </p>


                </div>


            </div>

            <div class="columns mt-6">
                <div class="column is-2">
                    <figure class="image is-128x128 has-background-warning"> 
                        <img src="" class="has-background-warning" alt="">
                    </figure>
                </div>
                <div class="column is-3">
                    <figure class="image is-4by5">
                        <img src="" class="has-background-warning" alt="">
                    </figure>
                </div>
                <div class="column is-3">
                    <figure class="image is-4by5">
                        <img src="" class="has-background-warning" alt="">
                    </figure>
                </div>
                <div class="column is-3">
                    <figure class="image is-4by5">
                        <img src="" class="has-background-warning" alt="">
                    </figure>
                </div>



            </div>
        </section>
    </div>
</template>

<script setup>
const { data: clients } = await useAsyncData('clients', () => queryContent('/clients').only(['image', 'client']).find())

</script>

<style>
figure.is-rounded {
    border-radius: 50% !important;
}

.has-background-secondary {
    background-color: #FFF000;
}
</style>