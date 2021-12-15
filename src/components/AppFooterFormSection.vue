<template>
    <section id="myform">
        <form>
            <div class="user-data">
                <label for="name">
                    <input id="name" type="text" placeholder="Your Name *">
                </label>

                <label for="email">
                    <input id="email" type="email" placeholder="Your email *">
                </label>

                <label for="subject">
                    <input id="subject" type="text" placeholder="Subject">
                </label>
            </div>

            <textarea id="message" rows="10" placeholder="Your Message *"></textarea>
        </form>
        <button class="btn main-btn">
            <a href="#"> send message </a>
        </button>
    </section>
</template>

<script>
export default {
    name: 'AppFooterFormSection'
}
</script>

<style lang="scss" scoped>
    #myform {
        text-align: center;
    }
    form {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;
        .user-data {
            display: flex;
            flex-flow: column wrap;
            justify-content: space-between;
        }
        #name, #email, #subject, #message {
            width: 100%;
            font-size: 1rem;
            padding: .5rem;
            border: 1px solid var(--clr-primary-200);
        }
    }
    button {
        margin: 2rem 0;
    }
</style>