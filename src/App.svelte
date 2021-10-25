<script>
// Import article svelte component
import Article from './Article.svelte';

  let articles = [
    {
      id: 1,
      title: "Google anuncia sus nuevos celulares ",
      description: "El pixel 6 y el 6 pro ya estan a la venta por $599 y $899.",
      thumbnail:
        "https://logo.clearbit.com/google.com",
      url: "http://hatena.ne.jp/in/congue/etiam/justo/etiam.xml?lectus=erat&aliquam=volutpat&sit=in&amet=congue&diam=etiam&in=justo&magna=etiam&bibendum=pretium&imperdiet=iaculis&nullam=justo&orci=in&pede=hac&venenatis=habitasse&non=platea&sodales=dictumst&sed=etiam&tincidunt=faucibus&eu=cursus&felis=urna&fusce=ut&posuere=tellus&felis=nulla&sed=ut&lacus=erat&morbi=id&sem=mauris&mauris=vulputate&laoreet=elementum&ut=nullam&rhoncus=varius&aliquet=nulla&pulvinar=facilisi&sed=cras&nisl=non&nunc=velit&rhoncus=nec&dui=nisi&vel=vulputate&sem=nonummy&sed=maecenas&sagittis=tincidunt&nam=lacus&congue=at&risus=velit&semper=vivamus&porta=vel&volutpat=nulla&quam=eget&pede=eros&lobortis=elementum&ligula=pellentesque&sit=quisque&amet=porta&eleifend=volutpat&pede=erat&libero=quisque&quis=erat&orci=eros&nullam=viverra&molestie=eget&nibh=congue&in=eget&lectus=semper&pellentesque=rutrum&at=nulla&nulla=nunc&suspendisse=purus&potenti=phasellus&cras=in&in=felis&purus=donec&eu=semper&magna=sapien&vulputate=a",
    },
    {
      id: 2,
      title: "Google anuncia Pixel pass.",
      description:
        "Es una suscripcion en “bundle” o combo que le da acceso a usuarios de pixel a google one, youtube premium, youtube music premium y mas..",
      url: "http://yolasite.com/nullam/varius.json?diam=ante&id=ipsum&ornare=primis&imperdiet=in&sapien=faucibus&urna=orci&pretium=luctus&nisl=et&ut=ultrices&volutpat=posuere&sapien=cubilia&arcu=curae&sed=donec&augue=pharetra&aliquam=magna&erat=vestibulum&volutpat=aliquet&in=ultrices&congue=erat&etiam=tortor&justo=sollicitudin&etiam=mi&pretium=sit&iaculis=amet&justo=lobortis&in=sapien&hac=sapien",
    },
    {
      id: 3,
      title: "Snapchat y Google hacen una alianza.",
      description: "En los nuevos celulares pixel, con solo tapear dos veces en la parte de atras se abre la aplicacion de snap con la camara abierta..",
      thumbnail:
        "https://logo.clearbit.com/snapchat.com",
      url: "https://free.fr/tristique/fusce.html?natoque=nec&penatibus=condimentum",
    },
  ];


</script>

<main>
  <h1>Daily Story News</h1>

  <section>
	  {#each articles as article}
	  	<Article {article} />

	  {/each}
  </section>
</main>

<style>
  main {
    max-width: 640px;
    margin: 0 auto;
  }

  h1 {
	font-family: 'Lora', serif;
    text-align: center;
	color: #A422E9;
	font-size: 24px;
  }
</style>
