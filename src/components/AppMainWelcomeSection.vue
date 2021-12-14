<template>
    <section id="welcome-section" class="container_small">
        <!-- section header -->
        <div class="section-title">
            <h2>Welcome to Fable</h2>
            <span class="section-subtitle">Fable daycare&comma; preschool&comma; and kindergarten</span>
            <img class="img-divider" src="../assets/img/header_divider.png" alt="styled divider">
        </div>
        <!-- section main -->
        <div class="section-main">
            
        </div>
    </section>
</template>


<script>
export default {
    name: 'AppMainWelcomeSection',
}
</script>

<style scoped lang="scss">
#welcome-section {
    margin: 3rem auto;
    .section-title {
        text-align: center;
        h2 {
             font-weight: 300;
        }
        .section-subtitle {
            color: var(--clr-secondary-200);
        }
    }
}
    
</style>
