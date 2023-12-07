<script>
  import image from "$lib/assets/magicpattern-iAR6yhCkrxc-unsplash.jpg";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
  import { onMount } from "svelte";
  gsap.registerPlugin(ScrollTrigger);

  onMount(() => {
    gsap.from(".gsap-img", {
      delay: 0,
      stagger: 0.1,
      duration: 3,
      scale: 2,
      //   opacity: .5,
      rotate: -40,
      ease: "power4.out",
    });

    gsap.from(".gsap-img", {
      duration: 6,
      css: {
        filter: "grayscale(100%)",
        filter: "blur(100px)",
        "-webkit-filter": "grayscale(100%)",
      },
      ease: "power4.out",
    });

    gsap.from(".gsap-img2", {
      duration: 6,
      css: {
        filter: "grayscale(100%)",
        filter: "blur(100px)",
        "-webkit-filter": "grayscale(100%)",
      },
      ease: "power4.out",
    });

    gsap.from(".blob", {
      duration: 4,
      scale: 0,
      ease: "Power4.easeInOut",
    });

    let tl = gsap.timeline();

    tl.from(".move", {
      delay: 2.6,
      y: "100%",
      duration: 1.2,
      ease: "Expo.easeOut",
      stagger: 0.5,
    });

    tl.to(".move", {
      delay: 0.5,
      y: "-102%",
      duration: 0.5,
      ease: "Expo.easeOut",
      stagger: 0.05,
    });

    tl.from(".move2", {
      delay: 2.6,
      y: "102%",
      duration: 1.2,
      ease: "Expo.easeOut",
      stagger: 0.5,
    });

    gsap.to(".gsap-img", {
      delay: 6,
      stagger: 0.1,
      duration: 5,
      scale: 2,
      opacity: 0,
      rotate: -40,
      ease: "power4.out",
    });

    gsap.from(".gsap-img2", {
      delay: 6,
      stagger: 0.1,
      duration: 5,
      scale: 2,
      opacity: 1,
      rotate: -40,
      ease: "power4.out",
    });

    gsap.to(".blob", {
      delay: 5,
      duration: 1,
      scale: 0,
      ease: "Power4.easeInOut",
    });
  });
</script>

<div class="mask">
  <img class="gsap-img" src={image} alt="" />
  <svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
    <path
      class="blob"
      fill=""
      d="M48.6,-56.4C54,-43.1,43.3,-21.6,37.7,-5.6C32.1,10.4,31.6,20.7,26.2,32.4C20.7,44,10.4,57,-3.3,60.3C-16.9,63.5,-33.8,57.1,-47.9,45.5C-62.1,33.8,-73.3,16.9,-72.4,0.9C-71.5,-15,-58.3,-30.1,-44.2,-43.3C-30.1,-56.5,-15,-68,3.3,-71.2C21.6,-74.5,43.1,-69.6,48.6,-56.4Z"
      transform="translate(100 100)"
    />
  </svg>
</div>

<style>
  .mask {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    /* background-color: black; */
    z-index: 10;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    mask: url("assets/mask-svg.svg");
  }

  svg {
    width: 30%;
    fill: rgb(143, 206, 255);
    z-index: 100;
    animation: move 10s ease-in-out infinite;
    transform-origin: 50% 50%;
    filter: blur(30px);
    opacity: 0.7;
  }

  @keyframes move {
    0% {
      transform: scale(1) rotate(5deg);
    }
    20% {
      transform: scale(0.9, 1) rotate(10deg);
    }
    40% {
      transform: scale(0.9, 1) rotate(20deg);
    }
    60% {
      transform: scale(1.1) rotate(10deg);
    }
    80% {
      transform: scale(1.1) rotate(5deg);
    }
    100% {
      transform: scale(1) rotate(10deg);
    }
  }
</style>
