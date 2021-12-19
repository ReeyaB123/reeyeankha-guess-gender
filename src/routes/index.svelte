<script>
    let username = "";
    let gender = "";
    async function getGender() {
  fetch('https://api.genderize.io/?name=' + username)
	.then((response) => response.json())
	.then((data) => {
  	username = data.name; // Path for name
  	gender = data.gender; // Path for gender
	});
}
</script>
<h1>Guess Gender</h1>

<form on:submit|preventDefault={getGender}>
    <label for="name">Name:</label>
    <input id="username" bind:value={username} type="text" />
    <button type="submit">Check</button>
</form>

<p>Gender: {gender}</p>