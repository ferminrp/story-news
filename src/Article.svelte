<script>
  export let article;
</script>

<a href={article.url}>
  <article>
    <div class="image-container">
      {#if article.thumbnail != null}
        <div class="image" style="background-image: url({article.thumbnail})" />
      {/if}
    </div>
    <div class="article-text">
      <h2>{article.title}</h2>
      <p>{article.description}</p>
    </div>
  </article>
</a>

<style>
  article {
    display: flex;
    color: black;
    max-width: 90vw;
    margin: 50px auto;
    gap: 10px;
    font-family: 'Inter', sans-serif;
  }

  .image-container {
    width: 94 px;
    display: flex;
    align-content: flex-start;
    justify-content: space-around;
    align-items: flex-start;
  }

  .image {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    background-position: 50% 50%;
    background-repeat: no-repeat;
    background-size: cover;
  }

  .article-text {
    display: flex;
    flex-direction: column;
    align-content: flex-start;
    justify-content: flex-start;
    align-items: flex-start;
    max-width: 811px;
    gap: 21px;
  }

  .article-text h2,
  .article-text p {
    margin: 0px;
  }

  h2 {
    color: #3D3C3C;
    font-size: 20px;
    font-weight: 700;
    line-height: 1;
  }

  p {
    color: #737373;
    font-size: 16px;
    line-height: 1;
  }
  
</style>
