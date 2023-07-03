<script>
	import { onMount } from 'svelte';

	// import model from "./model.svelte";
	import Model from './model.svelte';
	import Tormsp from './form-page.svelte';
	import Samp from './card-detail.svelte';
	// import { onMount } from 'svelte';
	let isOpen = false;
	let showmodel = false;
	let active;

	function toggleOpen() {
		isOpen = !isOpen;

		active = !active;
	}

	function toggleOpenclose() {
		showmodel = !showmodel;
	}

	let searchQuery = '';

	// List of car companies
	let carCompanies = [
		{ name: 'Lamborghini', logo: '/images/lamborgini-logo.jpg' },
		{ name: 'Ford', logo: '/images/Ford-logo.png' },
		{ name: 'B M W', logo: '/images/b m w-logo.jpg' },
		{ name: 'Mercedes', logo: '/images/mersades-car-logo.jpg' },
		{ name: 'Honda', logo: '/images/honda-logo.jpg' }

		//   { name: 'BMW', logo: '/images/bmw-car-logo.jpg' },
		// Add more car companies here
	];
	let filteredCarCompanies = [];

	function updateFilteredCarCompanies() {
		filteredCarCompanies = carCompanies.filter((car) => {
			return car.name.toLowerCase().includes(searchQuery.toLowerCase());
		});
	}
	onMount(updateFilteredCarCompanies);

	function handleSearchInput(event) {
		searchQuery = event.target.value;
		updateFilteredCarCompanies();
	}

	let carCompany = {
		name: 'Lamborghini',
		models: [
			{
				name: 'Aventador SVJ',
				info: 'Italian luxury sports car',
				image: '/image-name/aventador-svj.webp'
			},

			{
				name: ' Revuelto',
				info: 'Italian supercar',
				image: '/image-name/Revuelto _ Lamborghini.webp'
			},
			{
				name: 'Huracan EVO',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-Huracán-Evo-390x390.png'
			},
			{
				name: 'Huracan Evo RWD Spyder',
				info: 'Italian supercar',
				image: '/image-name/2022-Lamborghini-Huracan-Tecnica-1-411x411.jpg'
			},
			{
				name: ' 350 GT',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-350gt.png'
			},
			{
				name: '4000 GT ‘Flying Star II’',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-4000-GT-‘Flying-Star-II’.jpg'
			},
			{
				name: 'Miura Prototipo',
				info: 'Italian supercar',
				image: '/image-name/Yellow-Lamborghini-Miura.jpg'
			},
			{
				name: 'Sesto Elemento',
				info: 'Italian supercar',
				image: '/image-name/sesto_elemento_over_rev_01_m.webp'
			},
			{
				name: 'Urus',
				info: 'Italian luxury SUV',
				image: '/image-name/Lamborghini-Urus-390x390.png'
			}
		],
		name1: 'Ford',
		models1: [
			{
				name: 'Endeavour1 Model',
				info: 'maxico brand',
				image: '/fordimage/Endeavour1.webp'
			},

			{
				name: ' Fiesta Model',
				info: 'Italian supercar',
				image: '/fordimage/fiesta.webp'
			},
			{
				name: 'Figo-1 Model',
				info: 'Italian supercar',
				image: '/fordimage	/Figo1.webp'
			},
			{
				name: 'For-Ecosport Model',
				info: 'Italian supercar',
				image: '/fordimage/ford-ecosport.webp'
			},
			{
				name: 'Freestyle1 Model',
				info: 'Italian supercar',
				image: '/fordimage/Freestyle1.webp'
			},
			{
				name: 'Fusion Model',
				info: 'Italian supercar',
				image: '/fordimage/fusion-w.webp'
			},
			{
				name: 'Mondeo Model',
				info: 'Italian supercar',
				image: '/fordimage/mondeo.webp'
			},
			{
				name: 'Mustang Model',
				info: 'Italian supercar',
				image: '/fordimage/mustang.webp'
			}
		],
		name2: 'B M W',
		models2: [
			{
				name: 'x1 Model',
				info: 'Italian luxury sports car',
				image: '/bmWMODEL/3-series-gran-limousine-exterior-right-front-three-quarter-2.webp'
			},

			{
				name: '',
				info: 'M2 Model',
				image: '/bmWMODEL/5-series-exterior-right-front-three-quarter-4.webp'
			},
			{
				name: 'M340i Model',
				info: 'Italian supercar',
				image: '/bmWMODEL/Lamborghini-Huracán-Evo-390x390.png'
			},
			{
				name: 'Z4 Model',
				info: 'Italian supercar',
				image: '/bmWMODEL/2022-m340i-xdrive-exterior-right-front-three-quarter-2.webp'
			},
			{
				name: ' 350 GT',
				info: 'Italian supercar',
				image: '/bmWMODEL/BMW-X5-Right-Front-Three-Quarter-157119.webp'
			},
			{
				name: '4000 GT ‘Flying Star II’',
				info: 'Italian supercar',
				image: '/bmWMODEL/m2-exterior-right-front-three-quarter.webp'
			},
			{
				name: 'Miura Prototipo',
				info: 'Italian supercar',
				image: '/bmWMODEL/new-7-series-exterior-right-front-three-quarter-2.webp'
			},
			{
				name: 'Sesto Elemento',
				info: 'Italian supercar',
				image: '/bmWMODEL/new-x1-exterior-right-front-three-quarter-2.webp'
			},
			{
				name: 'Urus',
				info: 'Italian luxury SUV',
				image: '/bmWMODEL/x3-m40i-exterior-right-front-three-quarter.webp'
			},
			{
				name: 'Urus',
				info: 'Italian luxury SUV',
				image: '/bmWMODEL/z4-exterior-right-front-three-quarter.webp'
			}
		],
		name3: 'Mercedes',
		models3: [
			{
				name: 'Benz0E class',
				info: 'Italian luxury sports car',
				image: '/mercedes/Mercedes-Benz-E-Class-290320211237.jpg'
			},

			{
				name: ' Benz-EQB',
				info: 'Italian supercar',
				image: '/mercedes/Mercedes-Benz-EQB-071120221731.jpg'
			},
			{
				name: 'Benz-GLb model',
				info: 'Italian supercar',
				image: '/mercedes/Mercedes-Benz-GLB-180420231922.jpg'
			},
			{
				name: 'Benz-GLE model',
				info: 'Italian supercar',
				image: '/mercedes/Mercedes-Benz-GLE-160220201751.jpg'
			},
			{
				name: ' 350 GT',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-350gt.png'
			},
			{
				name: '4000 GT ‘Flying Star II’',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-4000-GT-‘Flying-Star-II’.jpg'
			},
			{
				name: 'Miura Prototipo',
				info: 'Italian supercar',
				image: '/image-name/Yellow-Lamborghini-Miura.jpg'
			},
			{
				name: 'Sesto Elemento',
				info: 'Italian supercar',
				image: '/image-name/sesto_elemento_over_rev_01_m.webp'
			},
			{
				name: 'Urus',
				info: 'Italian luxury SUV',
				image: '/image-name/Lamborghini-Urus-390x390.png'
			}
		],
		name4: 'Honda',
		models4: [
			{
				name: 'Honda city Model',
				info: 'Italian luxury sports car',
				image: '/honda/honda-city.webp'
			},

			{
				name: 'honda-amaze',
				info: 'Italian supercar',
				image: '/honda/honda-amaze.webp'
			},
			{
				name: 'honda-jazz',
				info: 'Italian supercar',
				image: '/honda/honda-jazz.webp'
			},
			{
				name: 'honda-wr-v',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-350gt.png'
			},
			{
				name: ' 350 GT',
				info: 'Italian supercar',
				image: '/image-name/Lamborghini-350gt.png'
			},
			{
				name: '4000 GT ‘Flying Star II’',
				info: 'Italian supercar',
				image: '/honda/honda-wr-v.webp'
			},
			{
				name: 'Miura Prototipo',
				info: 'Italian supercar',
				image: '/image-name/Yellow-Lamborghini-Miura.jpg'
			},
			{
				name: 'Sesto Elemento',
				info: 'Italian supercar',
				image: '/image-name/sesto_elemento_over_rev_01_m.webp'
			},
			{
				name: 'Urus',
				info: 'Italian luxury SUV',
				image: '/image-name/Lamborghini-Urus-390x390.png'
			}
		],
		filteredModels: [],
		searchQuery: ''
	};

	let mordata = '';
	let beta = carCompany.models;
	let bsta = '';

	function handleClickshow(companyName) {
		if (companyName == 'Lamborghini') {
			mordata = carCompany.models;
			console.log(mordata);
			bsta = carCompany.name;
			beta = mordata;
			filterModels(beta);
		} else if (companyName == 'Ford') {
			mordata = carCompany.models1;
			bsta = carCompany.name1;

			beta = mordata;
			filterModels(beta);
		} else if (companyName == 'B M W') {
			mordata = carCompany.models2;
			bsta = carCompany.name2;

			beta = mordata;
			filterModels(beta);
		} else if (companyName == 'Mercedes') {
			mordata = carCompany.models3;
			bsta = carCompany.name3;
			console.log(bsta);
			beta = mordata;
			filterModels(beta);
		} else if (companyName == 'Honda') {
			mordata = carCompany.models4;
			bsta = carCompany.name4;

			beta = mordata;
			filterModels(beta);
		}
	}
	// onMount(beta)

	// function move(){
	function filterModels(beta) {
		carCompany.filteredModels = beta.filter((model) =>
			model.name.toLowerCase().includes(carCompany.searchQuery.toLowerCase())
		);
	}
	// }
	// import { navigate } from "svelte-routing";

	// function goToPage(url) {
	//   navigate(url);
	// }
	onMount(() => {
		filterModels(carCompany.models); // Invoke the filterModels function with initial data
	});

	let showmore = true;
</script>

<main>
	<div class=" flex">
		<div class="flex">
			<div
				class="{isOpen
					? ' w-24'
					: 'w-60'} overflow-hidden flex flex-col h-screen p-3 duration-300 bg-gray-800 shadow"
			>
				<div class="space-y-3">
					<div class="flex items-center justify-between">
						<h2 class=" text-base font-bold text-white">
							<img class=" rounded-full w-16 h-16" src="/images/logoself.jpg" alt="" />
							CarPortal
						</h2>
						<button on:click={toggleOpen} class:active>
							<div class="bg-black w-7 h-7 rounded-full">
								<span class="text-white">&#10094;</span>
							</div>
						</button>
					</div>
					<div class="relative">
						<span class="absolute inset-y-0 left-0 flex items-center py-4">
							<button type="submit" class="p-2 focus:outline-none focus:ring">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									fill="none"
									viewBox="0 0 24 24"
									stroke-width="1.5"
									stroke="currentColor"
									class="w-6 h-6"
								>
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"
									/>
								</svg>
							</button>
						</span>
						<input
							type="search"
							name="Search"
							placeholder="Search..."
							class="w-full py-2 pl-10 text-sm rounded-md focus:outline-none"
							on:input={handleSearchInput}
						/>
					</div>
					<div class="flex-1">
						{#if filteredCarCompanies.length > 0}
							<ul class="pt-2 pb-4 space-y-1 text-sm">
								{#each filteredCarCompanies as Company (Company.name)}
									<li class="rounded-sm">
										<a
											href={null}
											on:click={handleClickshow(Company.name)}
											class=" cursor-pointer flex items-center overflow-hidden p-2 space-x-3 rounded-md"
										>
											<img
												class=" w-14 mb-2 hover:shadow-slate-300 rounded-full h-14 hover:scale-110"
												src={Company.logo}
												alt=""
											/>

											<span class="text-gray-100 hover:text-amber-300">{Company.name}</span>
										</a>
									</li>
								{/each}
								<li class="rounded-sm">
									<a
										href={null}
										class=" cursor-pointer hover:shadow-black flex items-center overflow-hidden p-2 space-x-3 rounded-md"
									>
										<!-- <img class=" w-12 mb-2 rounded-full h-12"  alt="+">  -->

										<span
											class="bg-black text-gray-100 text-center text-[2.6rem] font-thin p-[0.75rem] w-14 mb-2 rounded-full h-14"
											>+</span
										>
										<span class="text-gray-100 hover:text-amber-300">Add Company</span>
									</a>
								</li>
							</ul>
						{:else}
							<p>No matching cars found.</p>
						{/if}
					</div>
				</div>
			</div>
			<div class="car-container h-screen bg-amber-100 w-fit overflow-scroll p-6">
				<div class="relative mb-8">
					<span class="absolute inset-y-0 left-0 flex items-center py-4">
						<button type="submit" class="p-2 focus:outline-none focus:ring">
							<svg
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="1.5"
								stroke="currentColor"
								class="w-6 h-6"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z"
								/>
							</svg>
						</button>
					</span>
					<input
						type="search"
						name="Search"
						placeholder="Search..."
						class="w-full py-2 pl-10 text-sm rounded-md focus:outline-none"
						bind:value={carCompany.searchQuery}
						on:input={filterModels(beta)}
					/>
				</div>
				<div class="flex mb-6 justify-between">
					<button />
					<button on:click={toggleOpenclose} class=" w-40 h-[3rem] text-white bg-sky-600"
						><a href={null}>Add Car models</a></button
					>
				</div>
				{#if showmore}
					<!-- <Model {carCompany} /> -->
					<!-- {#if carCompany.name=='Lamborghini'} -->

					{#each carCompany.filteredModels as model}
						<div class="card hover:scale-105 transition-all">
							{#if bsta == 'Lamborghini'}
								<a href="https://www.supercars.net/blog/all-brands/lamborghini/lamborghini-models/">
									<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name} />
									<div class="car-name">{carCompany.name}</div>
								</a>
							{:else if bsta == 'Ford'}
								<a href="https://www.cardekho.com/cars/Ford">
									<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name1} />
									<div class="car-name">{carCompany.name1}</div>
								</a>
							{:else if bsta == 'B M W'}
								<a href="https://www.carwale.com/bmw-cars/">
									<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name2} />
									<div class="car-name">{carCompany.name2}</div></a
								>
							{:else if bsta == 'Mercedes'}
								<a href="www.google.com">
									<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name3} />
									<div class="car-name">{carCompany.name3}</div>
								</a>
							{:else if bsta == 'Honda'}
								<a href="https://www.cardekho.com/cars/Honda">
									<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name4} />
									<div class="car-name">{carCompany.name4}</div></a
								>
							{:else}
								<!-- <p>hi</p> -->
								<img class="car-image w-fit h-16" src={model.image} alt={carCompany.name} />
								<div class="car-name">{carCompany.name}</div>
							{/if}
							<div class="car-model">{model.name}</div>
							<div class="car-info">{model.info}</div>
						</div>
					{/each}
				{/if}
				<!-- <div {showmodel} ></div> -->
				<Tormsp {showmodel} on:click={toggleOpenclose} />
				<!-- {#each carCompany.models as model}
         <div class="card">
        <img class="car-image" src={carCompany.image} alt={carCompany.name}>
        <div class="car-name">{carCompany.name}</div>
          <div class="car-model">{model.name}</div>
         <div class="car-info">{model.info}</div>
        </div>
         {/each} -->
			</div>
		</div>
		<div class="  flex justify-center w-full items-center">
			<video id="background-video" autoplay loop muted>
				<source src="/image-name/pexels-ojyrai-7727416 (1080p).mp4" type="video/mp4" />
				<!-- Add additional source elements for different video formats (e.g., WebM, Ogg) -->
			</video>
			<div class=" absolute">
				<Samp />
			</div>
		</div>
	</div>
</main>

<style>
	#background-video {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100vh;
		z-index: -1;
	}
	.active {
		position: absolute;
		left: 77px;
	}
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

	.car-info:hover,
	.car-model:hover {
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
