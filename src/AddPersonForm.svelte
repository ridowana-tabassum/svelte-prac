<script>
    let name;
    let beltColour;
    let age;
    // let fighting = false;
    // let sneaking = false;
    // let running = false;
    let skills = [];
  
    const handleSubmit = () => {
      console.log(name, beltColour, age, skills);
    };
  </script>
  
  <form on:submit|preventDefault={handleSubmit}>
    <label for="name">Name:</label>
    <input type="text" id="name" placeholder='name' bind:value={name}>
    
    <label for="age">Age:</label>
    <input type="number" id="age" placeholder='age' bind:value={age}>
    
    <label for="skills">Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting" id="fighting">fighting<br>
    <input type="checkbox" bind:group={skills} value="sneaking" id="sneaking">sneaking<br>
    <input type="checkbox" bind:group={skills} value="running" id="running">running<br>
    
    <label for="beltColour">Belt colour:</label>
    <select id="beltColour" bind:value={beltColour}>
      <option value="black">black</option>
      <option value="orange">orange</option>
      <option value="brown">brown</option>
      <option value="white">white</option>
    </select>
    
    <button>Add Ninja</button>
  </form>
  