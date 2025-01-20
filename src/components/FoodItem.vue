<template>
    <div>
      <div v-on:click="increment">  
        <h2>
          {{ foodName }}
          <img src="/img_quality.svg" v-show="foodIsFavorite">
        </h2>
        <p>{{ foodDesc }}</p>
        <p id="red">You have clicked me {{ count }} times</p>
        <button v-on:click="toggleFavorite">Favorite</button>
      </div>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        count: 0,
        foodIsFavorite: this.isFavorite
      }
    },
    props: {
        foodName: {
            type: String,
            required: true
        },
        foodDesc: {
            type: String,
            required: false,
            default: 'Description not available',
            validator: function(value) {
              if( 20<value.length && value.length<50 ) {
                return true;
              }
              else {
                return false;
              }
            }
        },
        isFavorite: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        increment() {
            this.count++;
        },
        toggleFavorite() { 
          this.foodIsFavorite = !this.foodIsFavorite;
        },
        // toggleFavorite() { 
        //   this.isFavorite = !this.isFavorite;
        // }
    }
  };
</script>
  
<style>
  /* #app > div {
    border: dashed black 1px;
    display: inline-block;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
  #red {
    font-weight: bold ;
    color: rgb(144, 12, 12);
  } */
</style>