<template>
    <div>
        <section id="intro" class="hero" style="padding:0px;">
            <div class="hero-icons">
                <img src="../assets/img/code.png" alt="particles" width="160" height="160" class="img-two animate-fade">
                <img src="../assets/img/messages.png" alt="particles" width="150" height="150" class="img-five animate-float-y">
            </div>
            <header class="masthead">
                <div class="container px-5">
                    <div class="gx-5 align-items-center">
                        <transition appear
                                    appear-active-class="fade-enter-active"
                                    >
                            <div class="mb-5 mb-lg-0 text-center ">
                                <p>Hello,</p>
                                <h1>I'm Hayden Tan</h1>
                                <h1>Full Stack Software Developer</h1>
                                <p>From Kuala Lumpur</p>
                            </div>
                        </transition>
                        <br />
                        <br />
                        <div class="banner-bottom">
                            <div class="banner-bottom-img">
                                <img src="../assets/img/hero-illustration-two.png" width="700" height="550" class="img1" alt="Paralax">
                            </div>
                        </div>
                    </div>
                    <div>
                        <ul class="shape-group list-nostyle ">
                            <li class="shape shape-1" data-sal="slide-down" data-sal-duration="500" data-sal-delay="100"><img src="../assets/img/bubble-32.png" alt=""></li>

                            <li class="shape shape-2" data-sal="slide-left" data-sal-duration="500" data-sal-delay="200"><img src="../assets/img/bubble-33.png" width="800" height="500" alt=""></li>

                            <li class="shape shape-3" data-sal="slide-left" data-sal-duration="500" data-sal-delay="700"></li>

                            <li class="shape shape-4" data-sal="slide-left" data-sal-duration="500" data-sal-delay="700"><img src="../assets/img/bubble-14.png" alt=""></li>

                            <li class="shape shape-5" data-sal="slide-left" data-sal-duration="500" data-sal-delay="700"><img src="../assets/img/bubble-4.png" alt=""></li>

                            <li class="shape shape-6" data-sal="slide-left" data-sal-duration="500" data-sal-delay="700"><img src="../assets/img/bubble-30.png" alt=""></li>

                            <li class="shape shape-7" data-sal="slide-left" data-sal-duration="500" data-sal-delay="700"><img src="../assets/img/bubble-31.png" alt=""></li>

                        </ul>
                    </div>
                </div>
            </header>
        </section>
        <!--<aside @mousemove="onMousemove"
                :style="{ backgroundColor: `hsl(${x}, 80%, 50%)` }"
                lass="movearea">
            <div class="container px-5">
                <div class="row gx-5 justify-content-center">
                    <div class="col-xl-8">
                        <div class="h2  text-white mb-3">"An intuitive solution to a common problem that we all face, wrapped up in a single app! "</div>
                        <br />
                        <p class="text-white">Move your mouse across this area..</p>
                    </div>
                </div>
            </div>
        </aside>-->
        <aside class="text-center bg-gradient-primary-to-secondary">
        <div class="container px-5">
            <div class="row gx-5 justify-content-center">
                <div class="col-xl-8">
                    <div class="h2  text-white mb-3">" An intuitive solution to a common problem that we all face, wrapped up in a single app! "</div>
                </div>
            </div>
        </div>
    </aside>
    </div>
</template>

<script>

export default {
        name: 'Home',

        data() {
            return {
                x: 0
            }
        },
        methods: {
            onMousemove(e) {
                this.x = e.clientX
            },
         
        }

}
</script>
<style scoped>
    .movearea {
        transition: 0.3s background-color ease;
    }

    .fade-enter-active {
        animation: go 3s;
    }

    @keyframes go {
        from {
            opacity:0;
        }

        to {
            opacity:1;
        }
    }

</style>
