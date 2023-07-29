<template>
  <div id="recent-works">
    <section class=" py-6 my-6" :key="index" v-for="(row, index) in posts">
      <div class="columns" :class="{ 'is-centered': row.shift == 'center' }">
        <div class="column is-8" :class="{ 'is-offset-4-desktop': row.shift == 'right' }">
          <figure class="image has-background-white-bis">
            <nuxt-img provider="netlify" format="webp" sizes="sm:100vw md:50vw lg:800px" loading="lazy"
              :src="row.cover" />
          </figure>
          <div class="columns is-centered mt-3" v-if="row.header_type == 'split'">
            <div class="column is-4-desktop is-12-touch">
              <p class="title is-size-3-desktop is-size-4-touch">{{ row.title }}</p>
            </div>
            <div class="column is-6-desktop is-12-touch is-offset-2-desktop">
              <p class="is-size-5-desktop is-size-6-touch">{{ row.description }}</p>
              <br>
              <nuxt-link :to="row._path" class="has-text-dark has-text-weight-semibold is-underlined is-size-5">Learn more
                →</nuxt-link>
            </div>
          </div>
          <div class="columns  mt-3" v-if="row.header_type == 'para'">
            <div class="column is-6-desktop is-12-touch">
              <p class="title is-size-3-desktop is-size-4-touch">{{ row.title }}</p>
              <p class="is-size-5-desktop is-size-6-touch">{{ row.description }}</p>
              <br>
              <nuxt-link :to="row._path" class="has-text-dark has-text-weight-semibold is-underlined is-size-5">Learn more
                →</nuxt-link>
            </div>
            <!-- <div class="column is-6-desktop is-12-touch is-offset-2-desktop">
            </div> -->
          </div>
        </div>
      </div>
      <br>
      <br>
      <br>
    </section>
    <nuxt-link to="work" class="title mb-6 pb-6">All Projects →</nuxt-link>
    <br>
    <br>
  </div>
</template>

<script setup>
const data = [
  {
    'title': 'Atelier DS, handcrafted homewares',
    'description': "Through a sensitive mixed media approach, this musical number aims to help first\
                responders by\
                highlighting and visualizing the common feelings they have to deal with when doing their job. You won’t\
                know whether to laugh or cry",
    'link_to_read': null,
    'link_preview': null,
    'year_of_work': '2016 - 2018',
    'shift': 'center', // left , right, center
  },
  {
    'title': 'Atelier DS, handcrafted homewares',
    'description': "Through a sensitive mixed media approach, this musical number aims to help first\
                responders by\
                highlighting and visualizing the common feelings they have to deal with when doing their job. You won’t\
                know whether to laugh or cry",
    'link_to_read': null,
    'link_preview': null,
    'year_of_work': '2016 - 2018',
    'shift': 'left', // left , right, center
  },
  {
    'title': 'Atelier DS, handcrafted homewares',
    'description': "Through a sensitive mixed media approach, this musical number aims to help first\
                responders by\
                highlighting and visualizing the common feelings they have to deal with when doing their job. You won’t\
                know whether to laugh or cry",
    'link_to_read': null,
    'link_preview': null,
    'year_of_work': '2016 - 2018',
    'shift': 'right', // left , right, center
  },
];

const { data: posts } = await useAsyncData('work', () => queryContent('/work').only(['title', 'cover', 'description', 'time', 'shift', '_path', 'header_type']).find())

// const { posts:blogposts } = await useAsyncData('work', () => {queryContent('work').findOne()})


</script>

<style></style>