<script>
import Navigation from "$lib/components/Navigation.svelte"
</script>

<Navigation />

<section>
  <div class="triangles"></div>
  <div class="paper-tecture"></div>
  <!-- <div class="square"></div> -->
  <h1>
    <span class="riso">riso </span>
    <span class="text">text </span>
  </h1>

  <nav>
    <a href="/">Previous week</a>
    <a href="/lineart">Next week</a>
  </nav>
</section>


<style>
  section {
    position: relative;
    height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  .paper-tecture {
    position: absolute;
    mix-blend-mode: multiply;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100%;
    background-size: 50%;
    opacity: .6;
    background-image: url("https://img.freepik.com/free-photo/sky-with-lot-noise_1253-150.jpg?w=2000&t=st=1701972373~exp=1701972973~hmac=b2570a18bee7dad20b335771d8938f2ce4bbefad691c1f6fd1c00b14473a3f1d");
  }

  h1 {
    font-family: "Diskopia Flat";
    font-size: 30rem;
    font-family: 200;
    mix-blend-mode: multiply;
    color: rgb(4, 0, 255);
    line-height: 0.6em;
    text-align: center;
    animation-name: rainbow;
    animation-duration: 30s;
    animation-timing-function: ease;
    animation-iteration-count: infinite;
    animation-direction: normal;
  }

  @keyframes rainbow {
    0% {
      color: red;
      text-shadow: -4px 0px 4px magenta;
    }
    12.5% {
      color: orange;
      text-shadow: -4px 0px 4px red;
    }
    25% {
      color: yellow;
      text-shadow: -4px 0px 4px orange;
    }
    37.5% {
      color: greenyellow;
      text-shadow: -4px 0px 4px yellow;
    }
    50% {
      color: cyan;
      text-shadow: -4px 0px 4px greenyellow;
    }
    62.5% {
      color: RoyalBlue;
      text-shadow: -4px 0px 4px cyan;
    }
    75% {
      color: purple;
      text-shadow: -4px 0px 4px RoyalBlue;
    }

    87.5% {
      color: magenta;
      text-shadow: -4px 0px 4px purple;
    }
    100% {
      color: red;
      text-shadow: -4px 0px 4px magenta;
    }
  }

  .square {
    position: absolute;
    top: 30%;
    left: -10%;
    height: 130vh;
    aspect-ratio: 1;
    background-color: rgb(178, 178, 249);
    mix-blend-mode: multiply;
    transform: rotate(60deg);
    border-radius: 100%;
    opacity: .4;
  }

  .triangles {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    --size: 5px;
    background-image: conic-gradient(
      #fff 90deg,
      rgb(0, 0, 0) 0 136deg,
      #fff 0 313deg,
      #000 0
    );
    background-size: var(--size) var(--size);
    opacity: 0.3;
  }

  .riso {
  }

  .text {
  }

  img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  nav {
    position: fixed;
    top: bottom;
    height: 100vh;
    width: 100%;
    z-index: 99999;
    padding: 2rem;
    display: flex;
  }

  a {
    color: white;
    /* text-decoration: none; */
    font-size: 1.5rem;
  }

  a:nth-of-type(2) {
    position: fixed;
    right: 2rem;
    bottom: 2rem;
  }
</style>
