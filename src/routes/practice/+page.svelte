<!-- <script lang="ts">
  import GameOver from '$lib/components/GameOver.svelte';

  let randomNum = Math.floor(Math.random() * 50) + 1;
  let answer: number | null = null;
  let isCorrect: boolean | null = null;
  let isVisible: boolean = false;

  $: isButtonDisabled = answer === null;
  let tries: string[] = ['❤️', '❤️', '❤️', '❤️', '❤️'];

  function handleClick() {
    if (answer === randomNum) {
      answer = null;
      isCorrect = true;
      setTimeout(() => {
        isCorrect = false;
      }, 400);
      tries = ['❤️', '❤️', '❤️'];
      randomNum = Math.floor(Math.random() * 10) + 1;
    } else if (answer !== randomNum) {
      answer = null;
      isVisible = true;
      console.log(randomNum);
      setTimeout(() => {
        isVisible = false;
      }, 1000);

      tries = [...tries.splice(1, tries.length - 1)];
    }
  }
</script>

<div class="flex items-center justify-center h-screen">
  {#if tries.length === 0}
    <GameOver on:click={() => (tries = ['❤️', '❤️', '❤️', '❤️', '❤️'])} />
  {:else}
    <div
      class="container flex flex-col items-center justify-center h-full border {isCorrect
        ? 'bg-green-200'
        : ''} {isVisible ? 'bg-red-200' : ''}"
    >
      <strong class="py-2 text-5xl font-extrabold">Lives Left</strong>
      <div class="flex items-center gap-4">
        {#each tries as val}
          <p class="text-xl">{val}</p>
        {/each}
      </div>
      <div class="flex flex-col items-center justify-center py-10">
        {#if isCorrect}
          <span class="text-2xl font-bold text-green-500">You got it!</span>
        {:else if isVisible}
          <h2 class="text-2xl font-bold text-red-500">Wrong Guess</h2>
        {/if}

        <h2 class="text-xl font-bold">
          {isCorrect ? '' : 'Guess the Number to know my crush.'}
        </h2>
      </div>

      <div class="flex flex-col items-center gap-4">
        {#if !isCorrect}
          <input
            type="number"
            class="input input-bordered focus:outline-none"
            bind:value={answer}
            min="0"
            required
            disabled={isVisible}
          />
          <button
            type="submit"
            disabled={isButtonDisabled}
            on:click={handleClick}
            class="w-32 btn">Guess</button
          >
        {:else}
          <div class="border-black avatar">
            <div class="w-32 h-32 rounded-full">
              <img src="/qt.png" alt="my crush" />
            </div>
          </div>
          <span class="text-2xl font-bold">Fae Ganda!</span>
        {/if}
      </div>
    </div>
  {/if}
</div> -->
