<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap" rel="stylesheet">
</svelte:head>

<script>
  import { Router, Link, Route } from "svelte-routing";

  // Routes
  import Home from "./route/Home.svelte";
  import CreateNewPassword from "./route/CreateNewPassword.svelte";

  // Components
  import Topbar from './components/Topbar.svelte'
  import Button from './components/Button.svelte'

  export let url = "";
</script>

<Router url="{url}">
  <main>
    <Route path="/"><Home /></Route>
    <Route path="create-new-password" component="{CreateNewPassword}" />
  </main>
</Router>

<style>
  
</style>
