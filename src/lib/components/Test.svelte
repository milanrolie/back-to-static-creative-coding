<script>
  import image from "$lib/assets/magicpattern-iAR6yhCkrxc-unsplash.jpg";
  import { onMount } from "svelte";
  import MaskAmimation from "./MaskAmimation.svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
  gsap.registerPlugin(ScrollTrigger);

  onMount(() => {
    gsap.from(".sphere", {
        delay: 6,
      duration: 4,
      x: "100%",
      rotate: 5,
      ease: "Power4.easeOut",
    });

    gsap.from(".sphere", {
      rotate: 360,
      duration: 500,
    
    });

    gsap.from(".shadow", {
        delay: 6,
      duration: 4,
      x: "100%",
      ease: "Power4.easeOut",
    });
});

</script>

<section>
  <h1>
    <span class="creatief words"> <div class="move">Delayed Blurs</div> </span>
    <span class="webbureau words"> <div class="move">and gradients</div> </span>
    <span class="met ballen words"> <div class="move">page load</div> </span>
  </h1>

  <a href="/riso">
  <h1>
    <span class="creatief2 words2"> <div class="move2">Go to</div> </span>
    <span class="webbureau2 words2"> <div class="move2">next</div> </span>
    <span class="met ballen2 words2"> <div class="move2">week</div> </span>
  </h1>
</a>
  <MaskAmimation />

  <div class="background">
    <img class="gsap-img2 blur" src={image} alt="" />
    <div class="grain"></div>
    <div class="bg-1"></div>
  </div>
  <div class="sphere">
    <img src={image} alt="" />
  </div>
  <div class="shadow"></div>
</section>

<style>
  h1 {
    position: absolute;
    color: rgb(227, 227, 227);
    top: 47%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 100;
    font-size: 2.5rem;
    font-weight: 500;
    display: flex;
    gap: .5rem;
  }

  section {
    position: relative;
    height: 100vh;
    width: 100%;
    overflow: hidden;
    filter: grayscale(0);
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 1;
  }

  .blur {
    filter: blur(10px);
  }

  .background {
    position: relative;
    height: 100vh;
    width: 100%;
    background-color: rgb(184, 153, 255);
    background-image: radial-gradient(
        at 32% 85%,
        hsla(134, 88%, 69%, 1) 0px,
        transparent 50%
      ),
      radial-gradient(at 2% 37%, hsla(20, 60%, 71%, 1) 0px, transparent 50%),
      radial-gradient(at 71% 44%, hsla(323, 60%, 75%, 1) 0px, transparent 50%),
      radial-gradient(at 93% 56%, hsla(163, 82%, 67%, 1) 0px, transparent 50%),
      radial-gradient(at 79% 62%, hsla(298, 69%, 65%, 1) 0px, transparent 50%),
      radial-gradient(at 36% 18%, hsla(196, 68%, 63%, 1) 0px, transparent 50%),
      radial-gradient(at 76% 94%, hsla(274, 99%, 60%, 1) 0px, transparent 50%);
    filter: grayscale(0);
    animation: gradient-animation 1s ease infinite;

    @keyframes gradient-animation {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }
  }

  .sphere {
    position: absolute;
    top: -20%;
    right: -10%;
    height: 100vh;
    overflow: hidden;
    aspect-ratio: 1;
    border-radius: 100%;
    background-color: aqua;
    background-image: radial-gradient(
        at 32% 85%,
        hsla(134, 88%, 69%, 1) 0px,
        transparent 50%
      ),
      radial-gradient(at 2% 37%, hsla(20, 60%, 71%, 1) 0px, transparent 50%),
      radial-gradient(at 71% 44%, hsla(323, 60%, 75%, 1) 0px, transparent 50%),
      radial-gradient(at 93% 56%, hsla(163, 82%, 67%, 1) 0px, transparent 50%),
      radial-gradient(at 79% 62%, hsla(298, 69%, 65%, 1) 0px, transparent 50%),
      radial-gradient(at 36% 18%, hsla(196, 68%, 63%, 1) 0px, transparent 50%),
      radial-gradient(at 76% 94%, hsla(274, 99%, 60%, 1) 0px, transparent 50%);
    filter: grayscale(0.8);
    /* animation: rotate 500s infinite; */
  }

  @keyframes rotate {
    0% {
      transform: rotate(360deg);
    }

    100% {
      transform: rotate(0deg);
    }
  }

  .shadow {
    position: absolute;
    top: -20%;
    right: -10%;
    height: 100vh;
    aspect-ratio: 1;
    border-radius: 100%;
    box-shadow:
      rgba(50, 50, 93, 0.5) 0px 50px 100px -20px,
      rgba(0, 0, 0, 0.1) 0px 30px 60px -30px;
  }

  .grain {
    position: absolute;
    height: 100vh;
    text-align: left;
    isolation: isolate;
    z-index: 1000;
    pointer-events: none;
  }

  .grain:before {
    content: "";
    position: fixed;
    top: -150%;
    left: -100%;
    z-index: -1;
    width: 350%;
    height: 350%;
    background-image: url("assets/grain.png");
    opacity: 0.3;
  }

  .grain::before {
    animation: grain 5s steps(10) infinite;
  }

  @keyframes grain {
    0%,
    100% {
      transform: translate(0);
    }

    10% {
      transform: translate(-5%, -10%);
    }

    20% {
      transform: translate(-15%, 5%);
    }

    30% {
      transform: translate(7%, -25%);
    }

    40% {
      transform: translate(-5%, 25%);
    }

    50% {
      transform: translate(-15%, 5%);
    }

    60% {
      transform: translate(15%);
    }

    70% {
      transform: translateY(15%);
    }

    80% {
      transform: translate(3%, 35%);
    }

    90% {
      transform: translate(-10%, 10%);
    }
  }


  .words {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
  }



  .words2 {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
  }


</style>
