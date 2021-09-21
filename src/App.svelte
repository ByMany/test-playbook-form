<script lang="ts">
  import logo from './assets/svelte.png';
  import Counter from './lib/Counter.svelte';
  import Login from './Login.svelte';
  import PlaybookForm from './PlaybookForm.svelte';
  let name = '';
  let url = '';
  const log = (event: Event & { currentTarget: EventTarget & HTMLInputElement }) => {
    console.log(event.currentTarget.files);
    url = URL.createObjectURL(event.currentTarget.files[0]);
    document.getElementById('size').innerText = `${Math.floor(
      event.currentTarget.files[0].size / 1024
    )}kB`;
  };
</script>

<svelte:head>
  <link rel="stylesheet" href="https://unpkg.com/modern-css-reset/dist/reset.min.css" />
  <link rel="stylesheet" href="https://unpkg.com/sakura.css/css/sakura.css" type="text/css" />
</svelte:head>
<main>
  <article>
    <section>
      <h1>Hello {name}</h1>
    </section>
    <Login />
    <PlaybookForm />
  </article>
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Work+Sans:ital,wght@0,100;0,400;0,700;1,500&display=swap');
  @font-face {
    font-family: Sohne;
    src: url(src/assets/soehne-web-buch.woff) format('woff');
  }

  main,
  h1 {
    font-family: Sohne, 'Work Sans', sans-serif !important;
  }
</style>
