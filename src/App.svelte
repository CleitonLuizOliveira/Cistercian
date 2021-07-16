<script>
	let inputNumber = 0;
	$: shape = inputNumber.toString().padStart(4,0) || "0000";

	$: if (inputNumber > 9999) {
		inputNumber = 9999;
	} else if(!inputNumber || inputNumber < 0) {
		inputNumber = 0;
	}
</script>

<main>
	<div class="symbol">
		<div class="main_shape"></div>
		<div class="numeral bottom left">
			<img src={`images/${shape[0]}.png`} alt="">
		</div>
		<div class="numeral bottom right">
			<img src={`images/${shape[1]}.png`} alt="">
		</div>
		<div class="numeral top left">
			<img src={`images/${shape[2]}.png`} alt="">
		</div>
		<div class="numeral top right">
			<img src={`images/${shape[3]}.png`} alt="">
		</div>
	</div>
	<input type="number" bind:value={inputNumber}>
</main>

<style>
	.symbol {
		width: 360px;
		height: 360px;
		display: block;
		margin: 50px auto;
		box-sizing: border-box;
		position: relative;
	}

	.main_shape {
		display: block;
		background-color: black;
		width: 6.6%;
		height: 100%;
		position: absolute;
		left: 47.5%;
	}

	.numeral {
		display: block;
		width: 33%;
		height: 33%;
		position: absolute;
	}

	.left {
		left: 14.7%;
		transform: scaleX(-1);
	}

	.right {
		left: 54.1%;
	}

	.bottom {
		bottom: 0;
		transform: scaleY(-1);
	}

	.left.bottom {
		transform: scale(-1);
	}

	input {
		display: block;
		margin: 50px auto;
	}

	img {
		width: 100%;
	}
</style>