<template>
    <main>
        <AppMainWelcomeSection/>

        <AppMainOverviewSection/>

        <AppMainClassesSection/>

    </main>
</template>


<script>
import AppMainWelcomeSection from "./AppMainWelcomeSection.vue";
import AppMainOverviewSection from "./AppMainOverviewSection.vue";
import AppMainClassesSection from "./AppMainClassesSection.vue";

export default {
    name: 'AppMain',
    components: {
        AppMainWelcomeSection,
        AppMainOverviewSection,
        AppMainClassesSection,
    }
}
</script>

<style scoped lang="scss">

</style>