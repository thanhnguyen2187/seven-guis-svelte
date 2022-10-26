<script lang="ts">
  let count = 0

  function increase() {
      count += 1
  }
</script>

<div>
  <input type="text" bind:value={count}/>
  <button on:click={increase}>Increase</button>
</div>
