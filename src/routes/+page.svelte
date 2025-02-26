<script lang="ts">
	import '../app.css';
	import { onMount } from 'svelte';
	import mainFloor from '$lib/assets/images/main-floor.avif';
	import upperFloor from '$lib/assets/images/upper-floor.avif';

	type Room = {
		name: string;
		drawPath: Function;
	};

	const ROOMS: Room[] = [
		{
			name: 'Fellbach',
			drawPath: drawFellbachPath
		},
		{
			name: 'Mexicalli',
			drawPath: drawMexicalliPath
		},
		{
			name: 'Staefa',
			drawPath: drawStaefaPath
		},
		{
			name: 'Bron',
			drawPath: drawBronPath
		},
		{
			name: 'Plymouth',
			drawPath: drawPlymouthPath
		},
		{
			name: 'Vianen',
			drawPath: drawVianenPath
		},
		{
			name: 'Kitchener Centre',
			drawPath: drawKitchenerCentrePath
		},
		{
			name: 'Outer Space',
			drawPath: drawOuterSpacePath
		},
		{
			name: 'Baulkham Hills',
			drawPath: drawBaulkhamHillsPath
		},
		{
			name: 'Alicante',
			drawPath: drawAlicantePath
		},
		{
			name: 'Warrington',
			drawPath: drawWarringtonPath
		},
		{
			name: 'Giggle',
			drawPath: drawGigglePath
		},
		{
			name: 'Pop',
			drawPath: drawPopPath
		},
		{
			name: 'Purr',
			drawPath: drawPurrPath
		},
		{
			name: 'Rustle',
			drawPath: drawRustlePath
		},
		{
			name: 'Tweet',
			drawPath: drawTweetPath
		},
		{
			name: 'Vroom',
			drawPath: drawVroomPath
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

		ctx.beginPath();
		ctx.arc(385, 855, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function clearCanvas() {
		ctx.clearRect(0, 0, canvas.width * 2, canvas.height * 2);
	}

	function drawFellbachPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(470, 990);
		ctx.lineTo(415, 1480);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(415, 1480, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawMexicalliPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1090, 990);
		ctx.lineTo(1090, 1700);
		ctx.lineTo(1160, 1700);
		ctx.lineTo(1120, 2350);
		ctx.lineTo(975, 2300);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(975, 2300, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawStaefaPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1090, 990);
		ctx.lineTo(1090, 1700);
		ctx.lineTo(1160, 1700);
		ctx.lineTo(1120, 2820);
		ctx.lineTo(1320, 2820);
		ctx.lineTo(1330, 2640);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1330, 2640, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawBronPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1090, 990);
		ctx.lineTo(1090, 1700);
		ctx.lineTo(1160, 1700);
		ctx.lineTo(1120, 2820);
		ctx.lineTo(1700, 2820);
		ctx.lineTo(1700, 2640);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1700, 2640, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawPlymouthPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1090, 990);
		ctx.lineTo(1090, 1700);
		ctx.lineTo(1160, 1700);
		ctx.lineTo(1120, 2820);
		ctx.lineTo(1920, 2820);
		ctx.lineTo(1940, 2940);
		ctx.lineTo(2220, 2940);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(2220, 2940, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawVianenPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1610, 990);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1610, 990, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawKitchenerCentrePath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1400, 990);
		ctx.lineTo(1400, 1400);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1400, 1400, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawOuterSpacePath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(660, 280);
		ctx.lineTo(200, 280);
		ctx.lineTo(250, 50);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(250, 50, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawBaulkhamHillsPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(660, 320);
		ctx.lineTo(740, 320);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(740, 320, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawAlicantePath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(660, 250);
		ctx.lineTo(850, 250);
		ctx.lineTo(840, 325);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(840, 325, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawWarringtonPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(660, 250);
		ctx.lineTo(925, 250);
		ctx.lineTo(925, 320);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(925, 320, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawGigglePath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(580, 990);
		ctx.lineTo(1185, 990);
		ctx.lineTo(1185, 860);
		ctx.lineTo(1100, 860);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 860, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawPopPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(620, 655);
		ctx.lineTo(1185, 655);
		ctx.lineTo(1185, 725);
		ctx.lineTo(1100, 725);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 725, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawPurrPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(620, 655);
		ctx.lineTo(1185, 655);
		ctx.lineTo(1185, 570);
		ctx.lineTo(1100, 570);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 570, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawRustlePath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(620, 655);
		ctx.lineTo(1185, 655);
		ctx.lineTo(1185, 490);
		ctx.lineTo(1100, 490);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 490, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawTweetPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(620, 655);
		ctx.lineTo(1185, 655);
		ctx.lineTo(1185, 435);
		ctx.lineTo(1100, 435);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 435, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
	}

	function drawVroomPath() {
		ctx.beginPath();
		ctx.moveTo(385, 855);
		ctx.lineTo(590, 855);
		ctx.lineTo(620, 655);
		ctx.lineTo(1185, 655);
		ctx.lineTo(1185, 370);
		ctx.lineTo(1100, 370);
		ctx.stroke();
		ctx.closePath();
		ctx.beginPath();
		ctx.arc(1100, 370, 30, 0, 360, false);
		ctx.fill();
		ctx.closePath();
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
						room.drawPath();
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
				Select a Meeting Room
			</p>
		{/if}
	</div>
</main>
