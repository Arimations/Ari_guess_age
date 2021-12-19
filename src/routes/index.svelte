<script>

    let name = "" ;
    let gender = "" ;
    
    async function guessGender() {
      fetch('https://api.genderize.io/?name=' + name)
        .then((response) => response.json())
        .then((data) => {
          gender = data.gender; // Path for description
        });
    }
    
    </script>
    
    
    
    <h1>Guess Gender</h1>
    
    <form on:submit|preventDefault={guessGender}>
        <label for="name">Name:</label>
        <input id="name" bind:value={name} type="text" />
        <button type="submit">Check</button>
    </form>

    
<p>Gender: {gender}</p>
