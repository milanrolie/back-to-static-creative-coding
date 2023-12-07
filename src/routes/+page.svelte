<script>
  import App from '$lib/components/App.svelte'
  import Test from '../lib/components/Test.svelte';
  import Navigation from '../lib/components/Navigation.svelte';
</script>



<div>
  <!-- <App /> -->
  <!-- <Navigation /> -->
  <Test />
</div>


<style>
  :global(body) {
    margin: 0;
  }

  div {
    width: 100vw;
    height: 100vh;
    background: rgba(200, 217, 255, 0);
    /* background: linear-gradient(180deg, rgba(13, 19, 32, 1) 0%, rgba(8, 12, 21, 1) 100%); */
  }


  
</style>
