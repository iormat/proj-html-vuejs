<template>
    <main>
        <AppMainWelcomeSection/>

        <AppMainOverviewSection/>

        <AppMainClassesSection/>

        <AppMainStrenghtsSection/>

        <AppMainGallerySection/>

        <AppMainStaffSection/>

        <AppMainWhatsNewSection/>

        <AppMainMapsSection/>
    </main>
</template>


<script>
import AppMainWelcomeSection from "./AppMainWelcomeSection.vue";
import AppMainOverviewSection from "./AppMainOverviewSection.vue";
import AppMainClassesSection from "./AppMainClassesSection.vue";
import AppMainStrenghtsSection from "./AppMainStrenghtsSection.vue";
import AppMainGallerySection from "./AppMainGallerySection.vue";
import AppMainStaffSection from "./AppMainStaffSection.vue";
import AppMainWhatsNewSection from "./AppMainWhatsNewSection.vue";
import AppMainMapsSection from "./AppMainMapsSection.vue";

export default {
    name: 'AppMain',
    components: {
        AppMainWelcomeSection,
        AppMainOverviewSection,
        AppMainClassesSection,
        AppMainStrenghtsSection,
        AppMainGallerySection,
        AppMainStaffSection,
        AppMainWhatsNewSection,
        AppMainMapsSection,
    }
}
</script>

<style scoped lang="scss">

</style>