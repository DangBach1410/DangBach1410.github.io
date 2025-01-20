<template> 
  <h1>{{ message }}</h1>
  <h1>Food</h1>
  <div id="wrapper">
    <food-item food-name="Apples"
    food-desc="Apples are a good source of fiber and vitamin C."
    :is-favorite="false"
    />
    <food-item food-name="Pizza"
    :is-favorite="true"
    />
    <!-- <food-item food-name="Pizza"
    :is-favorite="true"
    /> -->
    <food-item food-name="Rice"
    :is-favorite="false"
    />
  </div>
</template>
<script>
  export default {
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }
</script>
<style>
  #app > div:hover {
    cursor: pointer;
  }
  #wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  #wrapper > div {
    border: dashed black 1px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
  img {
    height: 1.5em;
    float: right;
  }
</style>
