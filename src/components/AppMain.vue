<template>
    <main>
        <AppMainWelcomeSection/>

        <AppMainOverviewSection/>

        <AppMainClassesSection/>

        <AppMainStrenghtsSection/>

        <AppMainGallerySection/>

        <AppMainWhatsNewSection/>
    </main>
</template>


<script>
import AppMainWelcomeSection from "./AppMainWelcomeSection.vue";
import AppMainOverviewSection from "./AppMainOverviewSection.vue";
import AppMainClassesSection from "./AppMainClassesSection.vue";
import AppMainStrenghtsSection from "./AppMainStrenghtsSection.vue";
import AppMainGallerySection from "./AppMainGallerySection.vue";
import AppMainWhatsNewSection from "./AppMainWhatsNewSection.vue";

export default {
    name: 'AppMain',
    components: {
        AppMainWelcomeSection,
        AppMainOverviewSection,
        AppMainClassesSection,
        AppMainStrenghtsSection,
        AppMainGallerySection,
        AppMainWhatsNewSection,
    }
}
</script>

<style scoped lang="scss">

</style>