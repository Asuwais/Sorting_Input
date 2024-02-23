<script>
    let input = '';
    let sortedList = [];
    let reversedList = [];
  
    function sorting() {
      const numbers = [];
      const letters = [];
      const items = input.split('');
      for(let i in items){
        if (typeof items[i] == 'number'){
            numbers.push(items[i]);
        } else {
          letters.push(items[i]);
        }
      }
      numbers.sort((a, b) => a - b);
      letters.sort();
      sortedList = [...numbers, ...letters];
      reversedList = sortedList.slice().reverse();
    }
  </script>
  
  <div class="container">
    <h2 class = "lable" for="input">Enter numbers/letters:</h2>
    
    <input type="text" id="input" bind:value={input} />
    <button on:click={sorting}>Submit</button>
  
    <div class="list">
      <h3>Sorted List:</h3>
      <div class="items">
        {#each sortedList as item}
          <div class="item">{item}</div>
        {/each}
      </div>
    </div>
  
    <div class="list">
      <h3>Reversed List:</h3>
      <div class="items">
        {#each reversedList as item}
          <div class="item">{item}</div>
        {/each}
      </div>
    </div>
  </div>
  
  <style>
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
      border: 2px solid black;
      padding: 10px;
      border-radius: 4px;
      border-width: 2px;
    }
  
    .lable {
      font-size: 18px;
      margin-bottom: 10px;
    }
  
    input {
      padding: 5px;
      font-size: 16px;
      margin-bottom: 10px;
    }
  
    button {
      padding: 5px 10px;
      font-size: 16px;
      background-color: green;
      color: white;
      cursor: pointer;
    }
  
    .list {
      display: flex;
      flex-direction: column;
      margin-top: 20px;
    }
  
    h3 {
      font-size: 18px;
      margin-bottom: 10px;
    }
  
    .items {
      display: flex;
    }
  
    .item {
      margin-right: 10px;
      padding: 8px;
      font-size: 16px;
      background-color: lightgray;
      border-radius: 4px;
    }
  </style>