<template>
    <div>
        <section class="section">
            <div class="container-grid">
                <div class="Center-text">
                    <div class="has-text-centered">
                        <div class="is-size-3 has-text-centered" v-for="(nav, index) in navigation" :key="index">
                            <nuxt-link :to="nav.to" class="is-size-3 has-text-centered has-text-dark side-menu">
                                {{ nav.link_text }}
                            </nuxt-link>
                        </div>
                        <p class="title">Architechteu</p>
                        <p class="title">Test</p>
                        <p class="title">Two ds</p>
                    </div>
                </div>
                <div class="top-left">
                    <figure class="image my-4 is-3by2">
                        <img src="" class="has-background-dark" alt="">
                    </figure>
                </div>
                <div class="mid-left"></div>
                <div class="bottom-left"></div>
                <div class="top-right"></div>
                <div class="mid-right"></div>
                <div class="bottom-right"></div>
                <div class="mid-bottom"></div>
                <div class="mid-top"></div>
            </div>
        </section>
    </div>
</template>

<script>
const { data: navigation } = await useAsyncData('navigation', () => queryContent('/nav').only(['title', 'link_text']).find());
</script>

<style>
.container-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    gap: 0px 0px;
    grid-template-areas:
        "top-left mid-top top-right"
        "mid-left Center-text mid-right"
        "bottom-left mid-bottom bottom-right";
}

.Center-text {

    grid-area: Center-text;
}

.top-left {
    grid-area: top-left;
}

.mid-left {
    grid-area: mid-left;
}

.bottom-left {
    grid-area: bottom-left;
}

.top-right {
    grid-area: top-right;
}

.mid-right {
    grid-area: mid-right;
}

.bottom-right {
    grid-area: bottom-right;
}

.mid-bottom {
    grid-area: mid-bottom;
}

.mid-top {
    grid-area: mid-top;
}
</style>