<script>
    let name = "";
    let gender = "";
   
    async function guessgender() {
  fetch(' https://api.genderize.io/?name=' + name)
	.then((response) => response.json())
	.then((data) => {
  	gender=data.gender;
	});
}
</script>

<h1>Guess Gender</h1>

<form on:submit|preventDefault={guessgender}>
    <label for="name">Name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>
<p>Gender: {gender}</p>

