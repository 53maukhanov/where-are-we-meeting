<script lang="ts">
	import '../app.css';
	import { onMount } from 'svelte';
	import mainFloor from '$lib/assets/images/main-floor.avif';
	import upperFloor from '$lib/assets/images/upper-floor.avif';

	interface Point {
		x: number;
		y: number;
	}

	interface Room {
		name: string;
		path: Point[];
	}

	const ROOMS: Room[] = [
		{
			name: 'Fellbach',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 470, y: 990 },
				{ x: 415, y: 1480 }
			]
		},
		{
			name: 'Mexicalli',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1090, y: 990 },
				{ x: 1090, y: 1700 },
				{ x: 1160, y: 1700 },
				{ x: 1120, y: 2350 },
				{ x: 975, y: 2300 }
			]
		},
		{
			name: 'Staefa',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1090, y: 990 },
				{ x: 1090, y: 1700 },
				{ x: 1160, y: 1700 },
				{ x: 1120, y: 2820 },
				{ x: 1320, y: 2820 },
				{ x: 1330, y: 2640 }
			]
		},
		{
			name: 'Bron',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1090, y: 990 },
				{ x: 1090, y: 1700 },
				{ x: 1160, y: 1700 },
				{ x: 1120, y: 2820 },
				{ x: 1700, y: 2820 },
				{ x: 1700, y: 2640 }
			]
		},
		{
			name: 'Plymouth',
			path: [
				{ x: 385, y: 855 },
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1090, y: 990 },
				{ x: 1090, y: 1700 },
				{ x: 1160, y: 1700 },
				{ x: 1120, y: 2820 },
				{ x: 1920, y: 2820 },
				{ x: 1940, y: 2940 },
				{ x: 2220, y: 2940 }
			]
		},
		{
			name: 'Vianen',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1610, y: 990 }
			]
		},
		{
			name: 'Kitchener Centre',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1400, y: 990 },
				{ x: 1400, y: 1400 }
			]
		},
		{
			name: 'Outer Space',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 660, y: 280 },
				{ x: 200, y: 280 },
				{ x: 250, y: 50 }
			]
		},
		{
			name: 'Baulkham Hills',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 660, y: 320 },
				{ x: 740, y: 320 }
			]
		},
		{
			name: 'Alicante',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 660, y: 250 },
				{ x: 850, y: 250 },
				{ x: 840, y: 325 }
			]
		},
		{
			name: 'Warrington',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 660, y: 250 },
				{ x: 925, y: 250 },
				{ x: 925, y: 320 }
			]
		},
		{
			name: 'Giggle',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 580, y: 990 },
				{ x: 1185, y: 990 },
				{ x: 1185, y: 860 },
				{ x: 1100, y: 860 }
			]
		},
		{
			name: 'Pop',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 620, y: 655 },
				{ x: 1185, y: 655 },
				{ x: 1185, y: 725 },
				{ x: 1100, y: 725 }
			]
		},
		{
			name: 'Purr',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 620, y: 655 },
				{ x: 1185, y: 655 },
				{ x: 1185, y: 570 },
				{ x: 1100, y: 570 }
			]
		},
		{
			name: 'Rustle',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 620, y: 655 },
				{ x: 1185, y: 655 },
				{ x: 1185, y: 490 },
				{ x: 1100, y: 490 }
			]
		},
		{
			name: 'Tweet',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 620, y: 655 },
				{ x: 1185, y: 655 },
				{ x: 1185, y: 435 },
				{ x: 1100, y: 435 }
			]
		},
		{
			name: 'Vroom',
			path: [
				{ x: 385, y: 855 },
				{ x: 590, y: 855 },
				{ x: 620, y: 655 },
				{ x: 1185, y: 655 },
				{ x: 1185, y: 370 },
				{ x: 1100, y: 370 }
			]
		}
	];

	function loadImage(url: string) {
		return new Promise((resolve) => {
			const image = new Image();

			image.addEventListener('load', () => {
				resolve(null);
			});

			image.src = url;
		});
	}

	function onSearchInput(e: Event & { currentTarget: EventTarget & HTMLInputElement }) {
		const query = e.currentTarget.value.trim().toLowerCase();
		const filteredRooms = ROOMS.filter((room) => room.name.toLowerCase().includes(query));
		roomsList = filteredRooms;
	}

	function initCanvas() {
		ctx.drawImage(mainFloorImage, 0, 0);
		ctx.drawImage(upperFloorImage, 450, 2000);
	}

	function clearCanvas() {
		ctx.clearRect(0, 0, canvas.width * 2, canvas.height * 2);
	}

	function drawCircle(x: number, y: number) {
		ctx.beginPath();
		ctx.arc(x, y, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawPath(path: Point[]) {
		const start = path[0];
		const end = path[path.length - 1];

		drawCircle(start.x, start.y);

		ctx.beginPath();
		ctx.moveTo(start.x, start.y);

		for (let i = 1; i < path.length; i++) {
			const point = path[i];
			ctx.lineTo(point.x, point.y);
		}

		ctx.stroke();
		ctx.closePath();

		drawCircle(end.x, end.y);
	}

	let roomsList = $state(ROOMS);
	let currentRoom = $state('');

	let canvas: HTMLCanvasElement;
	let ctx: CanvasRenderingContext2D;

	let mainFloorImage: HTMLImageElement;
	let upperFloorImage: HTMLImageElement;

	const loadImagesPromise = Promise.all([loadImage(mainFloor), loadImage(upperFloor)]);

	onMount(() => {
		ctx = canvas.getContext('2d')!;
		ctx.lineWidth = 15;
		ctx.strokeStyle = 'red';
		ctx.fillStyle = 'red';
		ctx.scale(0.5, 0.5);
	});
</script>

<div class="hidden">
	<img src={mainFloor} alt="Main Floor" bind:this={mainFloorImage} />
	<img src={upperFloor} alt="Upper Floor" bind:this={upperFloorImage} />
</div>

<main class="flex h-dvh w-full">
	<menu class="relative flex min-w-72 flex-1 flex-col overflow-y-scroll">
		{#await loadImagesPromise}
			<p class="absolute top-1/2 left-1/2 -translate-1/2 text-center text-lg">Loading...</p>
		{:then _}
			<div class="sticky top-0 bg-white p-2">
				<input
					type="text"
					placeholder="Search for Meeting Room"
					class="w-full rounded-lg bg-gray-200 px-5 py-4 outline-none"
					oninput={onSearchInput}
				/>
			</div>

			{#each roomsList as room}
				<button
					class="cursor-pointer px-5 py-4 text-left hover:bg-gray-200"
					class:bg-blue-500!={currentRoom === room.name}
					class:text-white={currentRoom === room.name}
					onclick={() => {
						currentRoom = room.name;
						clearCanvas();
						initCanvas();
						drawPath(room.path);
					}}
				>
					{room.name}
				</button>
			{/each}
		{/await}
	</menu>

	<div class="relative flex-5 overflow-auto bg-blue-300" class:overflow-hidden={!currentRoom}>
		<canvas width="1320" height="1780" class="mx-auto" bind:this={canvas}></canvas>

		{#if !currentRoom}
			<p class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-center text-2xl">
				Select Meeting Room
			</p>
		{/if}
	</div>
</main>
