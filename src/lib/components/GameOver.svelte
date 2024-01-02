<script lang="ts">
  let show: boolean = false;
  setTimeout(() => {
    show = true;
  }, 1000);
</script>

<div class="flex flex-col items-center gap-3">
  <h1 class="font-extrabold text-7xl">Game Over!</h1>

  {#if show}
    <button
      type="submit"
      class="text-lg font-semibold bg-green-100 hover:bg-green-200 hover:outline-none btn"
      on:click>Guess Again!</button
    >
  {:else}
    <p>Restarting...</p>
  {/if}
</div>
