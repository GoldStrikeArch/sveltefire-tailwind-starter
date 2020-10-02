<script>
  let count = 0;
  function handleClick() {
    count++;
  }

  let disabled = true;
</script>

<style>
  .disabled {
    background: gray;
  }

  .img {
    width: 240px;
  }
</style>

<main class="bg-red-700">
  <button class="btn" class:disabled on:click={handleClick}> Click </button>
  <p>{count}</p>
</main>

<img
  class="img"
  src="https://images.unsplash.com/photo-1593642634315-48f5414c3ad9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
  alt="" />
