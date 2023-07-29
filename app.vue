<template>
  <div>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />

    <!-- <div v-show="showMobileNav.isOpen" class="blur-overlay"></div> -->
    <div class="hero  blur-overlay  is-fullheight-with-navbar has-background-transparent"
      v-if="showMobileNav.isOpen">
      <div class="hero-header ">
        <div class=" py-4 section container is-hidden-desktop">
          <div class="level  container is-mobile">
            <div class="level-left">
              <div class="level-item">
                <div>
                  <nuxt-link to="/" class="brandtype-mobile has-text-black ">SHINE BHOLA</nuxt-link>

                </div>
              </div>
            </div>
            <div class="level-right">
              <div class="level-item">
                <div>
                  <p @click="showNav" v-if="!showMobileNav.isOpen"
                    class="is-clickable has-text-weight-semibold has-text-dark">
                    Menu
                  </p>
                  <p @click="showNav" v-if="showMobileNav.isOpen"
                    class="is-clickable shas-text-weight-semibold has-text-dark">
                    Close
                  </p>

                </div>
              </div>
            </div>
          </div>
          <div class="mobile-nav">
            <p class="is-size-6">
              Shine Bhola, an architect, an academician and a photographer. Graduated as an architect from MNIT Jaipur and
              MFA in Photography from NID Ahmedabad and UCA Farnham.
            </p>
            <br>
            <ul>

              <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/" class="my-3 has-text-dark ">

                Home
              </nuxt-link>
              <li @click="showSubMobileNav.isOpen = !showSubMobileNav.isOpen"
                class="my-3 is-clickable has-text-dark is-size-6">

                Work
                <span v-if="!showSubMobileNav.isOpen" class="ml-2">+</span>
                <span v-if="showSubMobileNav.isOpen" class="ml-2">−</span>
              </li>
              <div class="" v-if="showSubMobileNav.isOpen">
                <li class="my-3" v-for="(nav, index) in navigation" :key="index">

                  <nuxt-link @click="() => { showMobileNav.isOpen = false }" :to="'/work/' + nav.link_text"
                    class="pl-6  has-text-dark  has-text-left  is-size-6 pr-3">

                    {{ nav.link_text }}
                  </nuxt-link>
                </li>

              </div>
              <li>
                <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/about"
                  class="my-3  has-text-dark  is-size-6">

                  About
                </nuxt-link>
              </li>
              <li class="mt-3">

                <nuxt-link @click="() => { showMobileNav.isOpen = false }" to="/contact"
                  class=" has-text-dark  is-size-6">

                  Contact
                </nuxt-link>
              </li>

            </ul>
          </div>
        </div>
      </div>
      <div class="hero-footer section">
        <ul>
          <li><a href="mailto:info@shinebhola.com" class="is-size-6 has-text-dark">info@shinebhola.com</a></li>
          <li><a href="tel:917073077042" class="is-size-6 has-text-dark">+91-7073077042</a></li>
          <li><a href="" class="is-size-6 has-text-dark">Facebook</a> - <a href=""
              class="is-size-6 has-text-dark">Instagram</a></li>
        </ul>
      </div>
    </div>
    <div class=" py-4 section container is-hidden-desktop">
      <div class="level  container is-mobile">
        <div class="level-left">
          <div class="level-item">
            <div>
              <nuxt-link to="/" class="brandtype-mobile has-text-black ">SHINE BHOLA</nuxt-link>

            </div>
          </div>
        </div>
        <div class="level-right">
          <div class="level-item">
            <div>
              <p @click="showNav" v-if="!showMobileNav.isOpen"
                class="is-clickable has-text-weight-semibold has-text-dark">
                Menu
              </p>
              <p @click="showNav" v-if="showMobileNav.isOpen"
                class="is-clickable shas-text-weight-semibold has-text-dark">
                Close
              </p>

            </div>
          </div>
        </div>
      </div>

    </div>
    <div class="section py-5   container">

      <!-- Type 2 -->
      <div class=" is-hidden-touch ">

        <div class="section container pt-0 px-0">
          <div class="level my-0">

            <div class="level-left">
              <nuxt-link to="/" class="brandtype has-text-black ">SHINE BHOLA</nuxt-link>
            </div>
            <!-- <div class="level-item">
            </div> -->
            <div class="level-right">
              <nuxt-link :class="{ 'main-item-active': route.path == '/' }" to="/"
                class="level-item main-item has-text-black mr-5 ">Home</nuxt-link>
              <nuxt-link to="/about" :class="{ 'main-item-active': route.path == '/about' }"
                class="level-item main-item has-text-black mr-5 ">About</nuxt-link>
              <nuxt-link to="/work" :class="{ 'main-item-active': route.path.includes('work') }"
                class="level-item main-item has-text-black  mr-5">Work</nuxt-link>
              <nuxt-link to="/contact" :class="{ 'main-item-active': route.path == '/contact' }"
                class="level-item main-item has-text-black">Contact</nuxt-link>
            </div>
          </div>
          <div class="level mb-0 py-0">
            <div class="level-left">

              <div class="level-item" v-for="(nav, index) in navigation" :key="index">
                <nuxt-link :to="'/work/' + nav.link_text" class=" has-hover has-text-dark heading tag is-notoutlined"
                  :class="{ 'tag is-outlined is-dark   is-rounded': route.params.work == nav.link_text }">

                  {{ nav.link_text }}
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="">
        <section class=" container ">
          <NuxtPage class="" />



        </section>
        <footer class="container has-background-transparent mt-6 px-0 pb-0 footer">

          <div class="level is-mobile">
            <div class="level-left">
              <div class="level-item">
                <div class="has-text-grey is-size-7-touch ">
                  ©️2023 Shine Bhola <br>
                  All Rights Reserved.
                </div>
              </div>
            </div>
            <div class="level-right">
              <div @click="scrollToTop" class="level-item main-item-active is-inline is-clickable">
                Scroll Back to Top ↑
              </div>
            </div>
          </div>
        </footer>
      </div>



    </div>
  </div>
</template>

<script setup>


const showMobileNav = reactive({
  isOpen: false
})
const showSubMobileNav = reactive({
  isOpen: false
})
const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());

function showNav() {
  showMobileNav.isOpen = !showMobileNav.isOpen
};
function scrollToTop() {
  window.scrollTo(0, 0);
};

const route = useRoute();

watch(route, value => {
  showMobileNav.isOpen = false
}, { deep: true, immediate: true });

const sub_navigation = [
  {
    'name': 'About',
    'to': '/about',
  },
  {
    'name': 'Clients',
    'to': '/clients',
  },
  {
    'name': 'Services',
    'to': '/services',
  },
  {
    'name': 'Contact',
    'to': '/contact',
  },
];
const follows = [
  {
    'name': 'Facebook',
    'to': '/',
  },
  {
    'name': 'Instagram',
    'to': '/',
  },
  {
    'name': 'Whatsapp',
    'to': '/',
  },
  {
    'name': 'Email',
    'to': '/',
  },
];
const abs_contact = [
  {
    'name': 'info@shinebhola',
    'link': 'mailto:info@shinebhola',
  },
  {
    'name': '+91-941-422-7723',
    'link': 'tel:+91-941-422-7723',
  },
];

</script>
<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
@import url('https://fonts.googleapis.com/css2?family=Figtree:wght@300;400;500;600;700;800;900&display=swap');

* {
  font-family: 'Figtree', sans-serif !important;
}

html {
  background-color: #fff;
}


.button-shine{
  border:none;
  border-radius:0;
  transition: 0.2s all ease-in;
  padding-bottom:3px;
  border-bottom:1px solid #000;
}
.button-shine:hover{
  transition: 0.2s all ease-in;
  /* border:none; */
  /* border-radius:0;
  padding-bottom:3px; */
  /* border-width:2px ; */
}

.brandtype {
  padding: 0 !important;
  font-size: 4rem;
  letter-spacing: 25px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

.brandtype-mobile {
  padding: 0 !important;
  font-size: 1rem;
  letter-spacing: 10px;
  /* animation: weights 5s linear ; */
  font-weight: 900;
}

.page-enter-active,
.page-leave-active {
  transition: all 0.4s ease-in;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
}

.title {
  letter-spacing: 2px;
  /* font-family: 'Moret' , 'Garamond', serif !important; */
  font-weight: normal !important;

}


.main-item {
  transition: 0.4s all ease-in;
}

.main-item:hover {
  border-bottom: 1px solid #0a0a0a;
  transition: 0.4s all ease-in;
}

.main-item-active {
  border-bottom: 1px solid #0a0a0a;
  transition: 0.4s all ease-in;
}

.side-menu {
  letter-spacing: 1px;
  /* font-family: 'Moret', 'Garamond', serif !important; */
}

html {
  scroll-behavior: smooth;
}

.has-background-transparent {
  background-color: rgba(255, 255, 255, 0);
}

.blur-overlay {
  height: 100%;
  width: 100vw;
  position: fixed;
  /* Stay in place */
  z-index: 1;
  /* Sit on top */
  left: 0;
  top: 0;
  transition: 1s all ease;
  background-color: #fefefe;
  /* Black fallback color */
  background-color: rgba(254, 254, 254, 0.9);
  backdrop-filter: blur(4px);
  /* filter: blur(3px); */
  /* Black w/opacity */
  overflow-x: hidden;

  /* Disable horizontal scroll */
}

.overlay-content {
  position: relative;
  top: 25%;
  /* 25% from the top */
  width: 100%;
  /* 100% width */
  text-align: center;
  /* Centered text/links */
  margin-top: 30px;
  /* 30px top margin to avoid conflict with the close button on smaller screens */
}

/* Msonary */

.masonry {
  column-count: 2;
  column-gap: 17px;
}

@media (min-width: 768px) {
  .masonry {
    column-count: 2;
  }
}

@media (min-width: 992px) {
  .masonry {
    column-count: 3;
  }
}

@media (min-width: 1199px) {
  .masonry {
    column-count: 3;
  }
}

.masonry .brick {
  box-sizing: border-box;
  -webkit-column-break-inside: avoid;
  page-break-inside: avoid;
  break-inside: avoid;
  /* counter-increment: 1; */
}

.masonry .image-mason {
  width: 100%;
  height: 100%;
  object-fit: cover;
}



.tag.is-notoutlined {
  background-color: #fff;
  text-decoration: none;
  transition: 0.2s all ease-in;
}

.tag.is-notoutlined:hover {
  background-color: rgb(240, 240, 240);
  border-radius: 9999px;
  ;

  /* text-decoration: none; */
}

a.tag:hover {
  text-decoration: none;
}

.tag.is-outlined.is-dark {

  border: 1px solid #0a0a0a;
  background-color: #fff;
  color: #0a0a0a;
  transition: 0.2s all ease-in;
}
</style>