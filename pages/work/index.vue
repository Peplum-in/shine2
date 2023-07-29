<template>
    <div id="recent-works">

        <section class="">
            <div class="masonry ">

                <div class="brick  " :key="index + 'images_item'"
                    v-for="(row, index) in posts">
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


        </section>

    </div>
</template>
  
<script setup>


const { data: posts } = await useAsyncData('work', () => queryContent('/work').find())


</script>
  