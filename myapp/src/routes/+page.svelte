
<h1>Basic Calculator</h1>

<script>
	let fnum = 0;
	let snum = 0;
	let sum = 0;

	function add(){
		return sum = fnum + snum;
	}
</script>

<input type="number" bind:value = {fnum} placeholder="First number" />
<input type="number" bind:value = {snum} placeholder="Second number "/>
<button on:click = {add}>Add</button>

<p>The sum is: {sum}</p>