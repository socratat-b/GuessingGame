<script lang="ts">
  let isCorrect: boolean = false;
</script>

<div class="flex items-center justify-center h-screen">
  <div
    class="container flex flex-col items-center justify-center h-full border {isCorrect
      ? 'bg-green-200'
      : ''}"
  >
    <strong class="py-2 text-5xl font-extrabold">Lives Left</strong>
    <div class="flex items-center gap-4">
      {#each ['❤️', '❤️', '❤️'] as val}
        <p class="text-xl">{val}</p>
      {/each}
    </div>
    <div class="flex flex-col items-center justify-center py-10">
      {#if isCorrect}
        <span class="text-2xl font-bold text-green-500">You got it!</span>
      {/if}

      <h2 class="text-xl font-bold">
        {isCorrect
          ? 'Here is my love of my life!'
          : 'Guess the Number to know my crush.'}
      </h2>
    </div>

    <div class="flex flex-col items-center gap-4">
      {#if !isCorrect}
        <input
          type="number"
          class="input input-bordered focus:outline-none"
          min="0"
        />
        <button
          type="submit"
          on:click={() => {
            isCorrect = true;
          }}
          class="w-32 btn">Guess</button
        >
      {:else}
        <div class="border-black avatar">
          <div class="w-32 h-32 rounded-full">
            <img src="/qt2.jpg" alt="my crush" />
          </div>
        </div>
        <span class="text-2xl font-bold">I love You! Ganda</span>
      {/if}
    </div>
  </div>
</div>
