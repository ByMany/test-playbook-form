<script lang="ts">
  let url = '';
  const log = (event: Event & { currentTarget: EventTarget & HTMLInputElement }) => {
    console.log(event.currentTarget.files);
    url = URL.createObjectURL(event.currentTarget.files[0]);
    document.getElementById('size').innerText = `${Math.floor(
      event.currentTarget.files[0].size / 1024
    )}kB`;
  };
</script>

<template>
  <section>
    <input type="file" name="file" id="ff" accept="image/png" on:change={log} />
    <img src={url} alt="" />
    <code id="size">0</code>
  </section>
</template>
