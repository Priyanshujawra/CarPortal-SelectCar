<script>
   let imageUrl = '';
  let carName = '';
  let carModel = '';
  let carInfo = '';
  let cardData = [];
  export let showmodel = false;
  function handleSubmit(event) {
    event.preventDefault();

    // Perform validation and save the data as per your requirements
    const newCard = {
      imageUrl,
      carName,
      carModel,
      carInfo
    };

    cardData = [...cardData, newCard];

    // Reset form fields
    imageUrl = '';
    carName = '';
    carModel = '';
    carInfo = '';
  }


    function removeCard(index) {
    cardData.splice(index, 1);
    cardData = [...cardData];

  }
  </script>
<div class="center">
  {#if showmodel}

  <div class="container p-8" >
    <span class=" text-3xl bg-white relative top-9 cursor-pointer" on:click >&#9747;</span>
    <form on:submit={handleSubmit}>
      <div class="form-group">
        <label for="imageUrl">Image URL:</label>
        <input type="text" id="imageUrl" bind:value={imageUrl} placeholder="Enter image URL" required />
      </div>
      <div class="form-group">
        <label for="carName">Car Name:</label>
        <input type="text" id="carName" bind:value={carName} placeholder="Enter car name" required />
      </div>
      <div class="form-group">
        <label for="carModel">Car Model:</label>
        <input type="text" id="carModel" bind:value={carModel} placeholder="Enter car model" required />
      </div>
      <div class="form-group">
        <label for="carInfo">Car Information:</label>
        <textarea id="carInfo" bind:value={carInfo} placeholder="Enter car information" required></textarea>
      </div>
      <div class="form-group">
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>
    {/if}
    <div class="card-container">
      {#each cardData  as card, index}
        <div class="card" key={index}>
          <img class="card-image" src={card.imageUrl} alt={card.carName} />
          <div class="card-name">{card.carName}</div>
          <div class="card-model">{card.carModel}</div>
          <div class="card-info">{card.carInfo}</div>
          <button on:click={() => removeCard(index)}>Remove</button>
        </div>
      {/each}
    </div>

</div>
  <style>

    .container {
        display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    left: 0;
    top: 0;
    background: #0000006e;
    position: absolute;
    padding: 20px;

    }



  /* Form styles */
  form {
    width: 400px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 4px;
    background-color: #fff;
    margin-bottom: 20px;
  }

  .form-group {
    margin-bottom: 20px;
  }

  label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
  }

  input[type="text"],
  textarea {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
  }

  button[type="submit"] {
    padding: 8px 16px;
    background-color: #4caf50;
    color: #fff;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
  }

  /* Card styles */
  .card-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .card {
    width: 300px;
    padding: 20px;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    margin: 10px;
    transition: transform 0.2s ease;
  }

  .card:hover {
    transform: scale(1.05);
  }

  .card-image {
    width: 100%;
    height: auto;
    margin-bottom: 10px;
    border-radius: 5px;
  }

  .card-name {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 10px;
    color: #333;
  }

  .card-model {
    font-size: 16px;
    color: #888;
    margin-bottom: 5px;
  }

  .card-info {
    font-size: 14px;
    color: #777;
  }

  button {
    padding: 8px 12px;
    background-color: #e74c3c;
    color: #fff;
    border: none;
    border-radius: 4px;
    font-size: 14px;
    cursor: pointer;
  }
  </style>
