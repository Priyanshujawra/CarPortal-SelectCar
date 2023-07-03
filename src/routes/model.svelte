
<script>

import { onMount } from 'svelte';

  export let carCompany ;


  export let filterModels;
  // onMount(filterModels);
  </script>

  <!-- {#each carCompany.models as model} -->
  {#each carCompany.filteredModels as model}
  <!-- {#if carCompany.name=='Lamborghini'} -->
    <div class="card hover:scale-105 transition-all" >
      <img class="car-image w-fit h-16" src={model.image} alt={carCompany.name}>
      <div class="car-name">{carCompany.name}</div>
      <div class="car-model">{model.name}</div>
      <div class="car-info">{model.info}</div>
    </div>
    <!-- {/each} -->
    {/each}


<style>
    .card {
   width: 300px;
   padding: 20px;
   color: deeppink;
   background-color: #f5f5f5;
   border-radius: 5px;
   box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
   margin-bottom: 20px;
 }

 .car-image {
   width: 100%;
   height: auto;
   margin-bottom: 10px;
   border-radius: 5px;
 }

 .car-name {
   font-size: 20px;
   font-weight: bold;
   /* text-decoration: underline; */
   margin-bottom: 10px;
   width: fit-content;

}

.car-info:hover,.car-model:hover {
    color: rgb(205, 71, 71);
}
.car-model {
     text-decoration: underline;
     cursor: pointer;
     padding: 1px;
     font-size: 16px;
     color: #1c1b1b;
     margin-bottom: 5px;
    }

    .car-info {
     text-decoration: underline;
     cursor: pointer;
     padding: 1px;
   font-size: 14px;
   color: #212020;
 }

</style>