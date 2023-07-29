<template>
    <div>
        <div class="masonry ">

            <div class="brick  " :key="index + 'images_item'"
                v-for="(row, index) in work">
                <div class="image-mason ">

                    <figure class="image  has-background-grey">
                        <nuxt-picture provider="netlify" sizes="sm:100vw md:50vw lg:600px" format="webp" width="400"
                            placeholder quality="80" loading="lazy" :src="row.image" />
                    </figure>
                    <div class=" mt-1 mb-4">
                    </div>
                </div>
            </div>



        </div>
        <div class="my-6"></div>
        <div class="columns mb-6 is-variable is-8 is-multiline">
            <div class="column is-4">
                <p class="heading">
                    ABOUT US</p>
                <p class="is-size-6">
                    Meet Shine Bhola, an architect, an academician and a photographer. Graduated as an architect from
                    MNIT Jaipur and MFA in Photography from NID Ahmedabad and UCA Farnham, United Kingdom in 2010.

                    <br>
                    In 2011, he established Shine Bhola Studios in Jaipur and is living his passion since then.
                </p>

            </div>

            <div class="column is-4">



                <p class="heading">
                    INFO</p>
                <p class=" ">

                <ul>


                    <li><a href="mailto:info@shinebhola.com" class=" is-size-6 has-text-dark">info@shinebhola.com</a></li>
                    <li><a href="tel:917073077042" class="is-size-6  has-text-dark">+91-7073077042</a></li>
                    <li class="">Facebook-<a href="" class="is-size-6 has-text-dark  is-underlined">@shinebhola</a>
                    </li>
                    <li class="">Instagram-
                        <a href="" class="is-size-6 has-text-dark  is-underlined">@shinebhola</a>
                    </li>
                </ul>


                </p>


            </div>
            <div class="column is-4">

                <p class="heading">
                    CLIENTS</p>
                <p class="">
                    BBC, Takenama, Durlabhji, Nila House, Conde Nast, Good Earth, Whirlpool, SDMH, SEDRAA'S School of
                    Architecture

                </p>

            </div>


        </div>


    </div>
</template>
<script setup>
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).find())


</script>