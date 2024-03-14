<script>
  let movies = [
    {title: 'За Палыча!', description: 'Отчественное кино о народном духе и братстве'},
    {title: 'Чебурашка', description: 'Отчественное кино о необычном существе, которое очень любит апельсины'},
    {title: 'Русы против ящеров', description: 'Отчественное кино о легендарной битве с зелеными негодяями'},

  ];

  function toggleDescription (movie)
  {
    movie.showDescription = !movie.showDescription;
  }
</script>

<style>
  .movie {
    margin: 10 px;
    display: inline-block;
    position: relative;
  }

  .movie:hover .description {
    display: block;
  }

  .description {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: lightgray;
    padding: 10px;
    border: 1px solid darkgray;
  }
</style>

{#each movies as movie}
  <div class="movie">
  <h3>{movie.title}</h3>
  <p on:mouseenter={() => toggleDescription(movie)} on:mouseleave={() => toggleDescription(movie)}>
    {#if movie.showDescription}
     <div class="description">{movie.description}</div>
    {/if}
  </div>
{/each}