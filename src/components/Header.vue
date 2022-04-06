<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light fixed-top shadow-sm" id="mainNav">
            <div class="container px-5">
               
                <a class="navbar-brand fw-bold" href="#intro">
                    <div class="logo">
                        <div class="pr-2"><img src="../assets/img/h2.png" width="30" height="30" alt="..." /></div>
                        <div>Portfolio</div>
                    </div>
                    
                </a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
                    Menu
                    <i class="bi-list"></i>
                </button>
                <div class="collapse navbar-collapse" id="navbarResponsive">
                    <ul class="navbar-nav ms-auto me-4 my-3 my-lg-0">
                        <li class="nav-item"><a class="nav-link me-lg-3" href="#about"><strong>About</strong></a></li>
                        <li class="nav-item"><a class="nav-link me-lg-3" href="#portfolio"><strong>Work</strong></a></li>
                        <li class="nav-item"><a class="nav-link me-lg-3" href="#contact"><strong>Contact</strong></a></li>
                    </ul>
                    <button class="btn btn-primary px-3 mb-2 mb-lg-0" onclick=" window.open('./Resume2200406.pdf','_blank')">
                        <span class="d-flex align-items-center">
                            <i class="bi bi-file-text me-2"></i>
                            <span class="small">Resume</span>
                        </span>
                    </button>
                </div>
            </div>
        </nav>
    </div>
</template>
<script>

    export default {
       
    }


</script>
<style>
</style>