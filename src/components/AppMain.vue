<template>
    <main>
        <AppMainWelcomeSection/>

        <AppMainOverviewSection/>

    </main>
</template>


<script>
import AppMainWelcomeSection from "./AppMainWelcomeSection.vue";
import AppMainOverviewSection from "./AppMainOverviewSection.vue";

export default {
    name: 'AppMain',
    components: {
        AppMainWelcomeSection,
        AppMainOverviewSection,
    }
}
</script>

<style scoped lang="scss">

</style>