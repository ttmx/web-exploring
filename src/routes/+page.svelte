<script>
	import Oscilloscope from '../components/Oscilloscope.svelte';
</script>

<div class="relative">
	<div class="absolute w-screen h-screen">
		<Oscilloscope />
	</div>
	<div
		class="absolute font-[Cantarell] w-screen h-screen flex flex-col justify-center items-center"
	>
		<div
			class="flex flex-row gap-4 justify-center items-center bg-mantle p-4 rounded-2xl drop-shadow-md backdrop-blur bg-opacity-80"
		>
			<div class="text-6xl font-extrabold text-text">Tiago <br /> Teles</div>
			<div
				class="grid grid-cols-1 grid-rows-4 gap-2 text-center justify-center items-center w-10 bg-base rounded-xl shadow-xl p-2"
			>
				<svg class="fill-mauve" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"
					><!--! Font Awesome Pro 6.3.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
						d="M392.8 1.2c-17-4.9-34.7 5-39.6 22l-128 448c-4.9 17 5 34.7 22 39.6s34.7-5 39.6-22l128-448c4.9-17-5-34.7-22-39.6zm80.6 120.1c-12.5 12.5-12.5 32.8 0 45.3L562.7 256l-89.4 89.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l112-112c12.5-12.5 12.5-32.8 0-45.3l-112-112c-12.5-12.5-32.8-12.5-45.3 0zm-306.7 0c-12.5-12.5-32.8-12.5-45.3 0l-112 112c-12.5 12.5-12.5 32.8 0 45.3l112 112c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256l89.4-89.4c12.5-12.5 12.5-32.8 0-45.3z"
					/></svg
				>
				<svg class="fill-maroon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"
					><!--! Font Awesome Pro 6.3.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
						d="M64 32C28.7 32 0 60.7 0 96v64c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64zm280 72a24 24 0 1 1 0 48 24 24 0 1 1 0-48zm48 24a24 24 0 1 1 48 0 24 24 0 1 1 -48 0zM64 288c-35.3 0-64 28.7-64 64v64c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V352c0-35.3-28.7-64-64-64H64zm280 72a24 24 0 1 1 0 48 24 24 0 1 1 0-48zm56 24a24 24 0 1 1 48 0 24 24 0 1 1 -48 0z"
					/></svg
				>
				<svg class="fill-yellow" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"
					><!--! Font Awesome Pro 6.3.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
						d="M256 384c9.6-31.9 29.5-59.1 49.2-86.2l0 0c5.2-7.1 10.4-14.2 15.4-21.4c19.8-28.5 31.4-63 31.4-100.3C352 78.8 273.2 0 176 0S0 78.8 0 176c0 37.3 11.6 71.9 31.4 100.3c5 7.2 10.2 14.3 15.4 21.4l0 0C66.5 324.9 86.4 352.1 96 384H256zM176 512c44.2 0 80-35.8 80-80V416H96v16c0 44.2 35.8 80 80 80zM96 176c0 8.8-7.2 16-16 16s-16-7.2-16-16c0-61.9 50.1-112 112-112c8.8 0 16 7.2 16 16s-7.2 16-16 16c-44.2 0-80 35.8-80 80z"
					/></svg
				>
				<svg class="fill-green" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"
					><!--! Font Awesome Pro 6.3.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
						d="M317.4 44.6c5.9-13.7 1.5-29.7-10.6-38.5s-28.6-8-39.9 1.8l-256 224C.9 240.7-2.6 254.8 2 267.3S18.7 288 32 288H143.5L66.6 467.4c-5.9 13.7-1.5 29.7 10.6 38.5s28.6 8 39.9-1.8l256-224c10-8.8 13.6-22.9 8.9-35.3s-16.6-20.7-30-20.7H240.5L317.4 44.6z"
					/></svg
				>
			</div>
		</div>
	</div>
</div>
