<script setup>
    import ClientList from './ClientList.vue'
</script>

<template>
    <main class="main">
        <figure class="main__hero-banner">
            <picture>
                <source media="(min-width: 1024px)" srcset="../../assets/images/image-hero-desktop.png">
                <img src="../../assets/images/image-hero-mobile.png"
                    alt="Hero Banner, a black man wearing white cloth holding a notebook" />
            </picture>
        </figure>
        <article class="main__article">
            <h1>Make remote work</h1>
            <p>Get you team in sync, no matter your location. Streamline processes, create team rituals, and watch
                productivity soar.</p>
            <button type="button">
                Learn more
            </button>
            <ClientList />
        </article>
    </main>
</template>