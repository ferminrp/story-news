<script>
  // Import article svelte component
  import Article from "./Article.svelte";
  import Date from "./Date.svelte";
  import { BarLoader } from "svelte-loading-spinners";


  let articles = null;
  let articlesDates;

  // fetch json from api and store it in variable articles

  var myHeaders = new Headers();
  myHeaders.append(
    "apikey",
    "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlhdCI6MTYzNTEyNTE4NSwiZXhwIjoxOTUwNzAxMTg1fQ.jqK1A4a0PaSoZelpZ0SZ3vgDNEjK25GZGmxwjRkDftQ"
  );

  let requestOptions = {
    method: "GET",
    headers: myHeaders,
    redirect: "follow",
  };

  fetch(
    "https://tpcxqzojgdjbrcxtrnjd.supabase.co/rest/v1/articles?select=*&limit=30&order=date.desc",
    requestOptions
  )
    .then((response) => response.json())
    .then((data) => {
      articles = data;
      // extract unique dates from articles
      articlesDates = Object.keys(articles.reduce((r,{date}) => (r[date]='', r) , {}))
    })
    .catch((error) => console.log("error", error));
</script>

<main>
  <h1>Tech Briefs</h1>

  <section>
    {#if articles !== null}
      {#each articlesDates as date}
        <Date {date} />
        {#each articles.filter(article => article.date == date) as article}
        <Article {article} />
        {/each}
      {/each}
    {:else}
      <div class="loading-container">
        <BarLoader color="#a422e9" />
      </div>
    {/if}
  </section>
</main>

<style>
  main {
    max-width: 640px;
    margin: 0 auto;
    padding-top: 1rem;
    padding-bottom: 2rem;
  }

  h1 {
    font-family: "Lora", serif;
    text-align: center;
    color: #a422e9;
    font-size: 24px;
    font-weight: 600;
  }


  .loading-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50vh;
    width: 100%;
  }
</style>
