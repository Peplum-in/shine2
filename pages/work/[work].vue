<template>
    <div v-if="work && page">

        <p class="mb-4 is-hidden-desktop heading tag is-outlined is-dark  is-rounded ">

            {{ text_string }} </p>

        <div class="masonry ">

            <div class="brick " :key="index + 'images_item'"
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

    </div>
</template>
<script setup>
const route = useRoute();
function getCapitalizedText(text) {
    return text[0].toUpperCase() + text.substring(1)
}
const photo_string = getCapitalizedText(route.params.work) + ' Photography';
const text_string = getCapitalizedText(route.params.work);
const { data: work } = await useAsyncData('work', () => queryContent('/work').only(['image', 'caption']).where({ 'tag': photo_string }).find())
const { data: page } = await useAsyncData('nav', () => queryContent('/nav').where({ 'title': photo_string }).find())


</script>
