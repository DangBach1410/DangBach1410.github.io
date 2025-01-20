<template> 
  <h1>{{ message }}</h1>
  <h1>Food</h1>
  <button @click="removeItem">Remove Item</button>
  <div id="wrapper">
    <food-item 
      v-for="x in foods"
      :key="x.name"
      :food-name="x.name"
      :food-desc="x.desc"
      :is-favorite="x.favorite"
    />
    <!-- <food-item food-name="Apples"
    food-desc="Apples are a good source of fiber and vitamin C."
    :is-favorite="false"
    />
    <food-item food-name="Pizza"
    :is-favorite="true"
    /> -->
    <!-- <food-item food-name="Pizza"
    :is-favorite="true"
    /> -->
    <!-- <food-item food-name="Rice"
    :is-favorite="false"
    /> -->
  </div>
</template>
<script>
  export default {
    data() {
      return {
        message: 'Hello Vue!',
        foods: [
          { name: 'Apples', desc: 'Apples are a good source of fiber and vitamin C.', favorite: false },
          { name: 'Pizza', desc: 'Pizza is a popular fast food.', favorite: true },
          { name: 'Rice', desc: 'Rice is a staple food in many countries.', favorite: false }
        ]
      }
    },
    methods: {
      removeItem() {
        this.foods.splice(1,1);
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
