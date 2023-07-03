<script>
  import { onMount  } from "svelte";
  let huracanEvo = {
    name: 'Lamborghini Huracan Evo',
    price: 'US$261,274',
    engine: '5.2L Nat Aspirated V10',
    power: '631 hp @ 8,000 rpm',
    torque: '443 lb-ft @ 6,500 rpm',
    acceleration: '0-60 mph: 2.9 seconds',
    topSpeed: 'Top Speed: 202 mph',
    image: '/image-name/Lamborghini-Huracán-Evo-390x390.png'
  };
  let videoUrls = ['/image/pexels-ojyrai-7727416 (1080p).mp4', '/image/pexels-taryn-elliott-5309420 (1080p).mp4', '.image/production_id_4560094 (2160p).mp4'];
  let currentIndex = 0;
  let currentVideoUrl = '';

  function playNextVideo() {
    currentVideoUrl = videoUrls[currentIndex];
    currentIndex = (currentIndex + 1) % videoUrls.length;
  }

  onMount(() => {
    // Initial video play
    playNextVideo();

    // Switch to the next video every 10 seconds
    setInterval(playNextVideo, 10000);
  });
</script>
<div>

<div class="card ">

  <img class="card-image" src={huracanEvo.image} alt={huracanEvo.name} />
  <div class="card-title">{huracanEvo.name}</div>
  <div class="card-info">
    <div><strong>Base price:</strong> {huracanEvo.price}</div>
    <div><strong>Engine:</strong> {huracanEvo.engine}</div>
    <div><strong>Power:</strong> {huracanEvo.power}</div>
    <div><strong>Torque:</strong> {huracanEvo.torque}</div>
    <div><strong>Acceleration:</strong> {huracanEvo.acceleration}</div>
    <div><strong>{huracanEvo.topSpeed}</strong></div>
  </div>
</div>
</div>
<style>

  .card {
    width: 300px;
    padding: 20px;
    background-color: #ffffff36;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    margin: 10px;
  }

  .card-image {
    width: 100%;
    height: auto;
    margin-bottom: 10px;
    border-radius: 5px;
  }

  .card-title {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 10px;
    color: #f315d3;
  }

  .card-info {
    font-size: 14px;
    color: rgb(226, 161, 96);
  }
</style>
