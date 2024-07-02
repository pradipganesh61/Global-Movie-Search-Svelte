<script>
  export let data;    //data are present here
</script>

<div class="result">
  <div class="divider">
    <h2 class="title">{data.Title}</h2>
    <img src={data.Poster} alt="movie_poster" class="poster" />
  </div>
  <div class="divider dividerSec">
    <p>{data.Plot ? data.Plot : ""}</p>
    <p>Stars: {data.Actors ? data.Actors : ""}</p>
    <p>Writer: {data.Writer ? data.Writer : ""}</p>
    <p>Director: {data.Director ? data.Director : ""}</p>
    <p>Duration: {data.Runtime ? data.Runtime : ""}</p>
    <ul>
      <p>Ratings</p>
      {#each data.Ratings as rate}
        <li>
          {rate.Source ? rate.Source : ""} | {rate.Value ? rate.Value : ""}
        </li>
      {/each}
    </ul>
    <a href={`https://www.imdb.com/title/${data.imdbID}`} target="_blank">
      <img src="1200px-IMDB_Logo_2016.svg.png" class="imdb" alt="imdb" />
    </a>
  </div>
</div>

<style>
  .imdb {
    width: 50px;
    height: auto;
    object-fit: contain;
  }
  .result {
    display: flex;
  }
  .dividerSec {
    padding: 2.5em 10em;
  }
</style>
