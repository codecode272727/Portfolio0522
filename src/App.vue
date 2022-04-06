<template>
    <div id="app">
        <Header></Header>
        <Home></Home>
        <About></About>
        <Work></Work>
        <Contact></Contact>
        <Footer></Footer>


    </div>
</template>
<script>
    import Header from './components/Header.vue';
    import Home from './views/Home.vue';
    import About from './views/About.vue';
    import Work from './views/Work.vue';
    import Footer from './views/Footer.vue';
    import Contact from './views/Contact.vue';


    export default {
        name: 'App',
        components: {
            Header,
            Home,
            About,
            Work,
            Footer,
            Contact,

        },


    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }

    #nav {
        padding: 30px;
    }

        #nav a {
            font-weight: bold;
            color: #2c3e50;
        }

            #nav a.router-link-exact-active {
                color: #42b983;
            }

    .slide-enter-active {
        animation: slide-in 200ms ease-out forwards;
    }

    .slide-leave-active {
        animation: slide-out 200ms ease-out forwards;
    }

    @keyframes slide-in {
        from {
            transform: translateY(-30px);
            opacity: 0;
        }

        to {
            transform: translateY(0);
            opacity: 1;
        }
    }

    @keyframes slide-out {
        from {
            transform: translateY(0);
            opacity: 1;
        }

        to {
            transform: translateY(-30px);
            opacity: 0;
        }
    }

    .header {
        position: fixed;
        top: 0;
        width: 100%
    }

    .img1 {
        z-index: 5;
        height: auto !important;
    }

    .img2 {
        z-index: 5;
    }

    @media (max-width:767px) {
        .img2 {
            max-width: 100%;
            max-height: 100%;
        }

        .portfolioImg {
            min-height: 200px;
        }
    }

    @media (min-width:768px) {
        .img2 {
            max-width: 60%;
            height: 60%;
        }

        .portfolioImg {
            min-height: 180px;
        }
    }

    @media (min-width:992px) {
        .img2 {
            max-width: 400px;
            max-height: 400px;
        }

        .portfolioImg {
            min-height: 202px;
        }
    }

    @media (min-width:1200px) {
        .img2 {
            max-width: 400px;
            max-height: 400px;
        }

        .portfolioImg {
            min-height: 220px;
        }
    }

    video {
        width: 100%;
        height: auto;
    }

    .contact-list .contact-row .contact-item {
        display: flex;
        align-items: center;
        padding: 3px;
    }
</style>
