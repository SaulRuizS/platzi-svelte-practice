<script>
  const movies = [
    {
      name: "Matrix",
      quantity: 0,
      available: 5
    },
    {
      name: "The Last Of Us",
      quantity: 0,
      available: 8
    },
    {
      name: "Spider Man",
      quantity: 0,
      available: 11
    }
  ];
</script>

{#each movies as movie}
<form>
  <h3>
    {movie.name}
  </h3>

  <button type="button" 
    on:click={
      () => movie.quantity -= 1
    }
    disabled={
      movie.quantity <= 0
    }  
  >
    -
  </button>

    {movie.quantity}
  
  <button type="button" 
    on:click={
      () => movie.quantity += 1
    }
    disabled={
      movie.quantity >= movie.available
    }  
  >
    +
  </button>
</form>
{/each}