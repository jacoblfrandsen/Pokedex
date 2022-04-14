<template>
<div class="home">
  <section class="image-gallery">
    <div class="image">
      
      <img :src="item.path" />
        
    </div>
   
    <div class="check">Guess Pokemon Name: <input name="pokemonname" v-model="pokemonname">
    <button @click="check()">Check</button>
    <p>{{ result }} </p>
    
    </div>

  </section>
</div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios';
export default {
  name: 'Home',
  data() {
    return {
     item: null,
     title: "",
     result: "",
     pokemonname: "",
    name: "",
    i: 0,
    

    }
  },
  created() {
    this.getItem();
    this.checkName();
  },
  methods: {
    async getItem() {
      try {
        let response = await axios.get("/api/items");
        this.item = response.data.at(this.i);
        
        return true;
      } catch (error) {
        console.log(error);
      }
    },
    check() {
        if(this.pokemonname == this.item.title)
        {
            this.result = "Correct";
        }
        else{
            this.result = " Incorrect" + " Correct answer was: " + this.item.title;
        }
        this.i = this.i + 1;
        this.getItem();
    },
    async checkName() {
      try {
        if (this.item.title == this.title)
            return true;
      } catch (error) {
        console.log(error);
      }
    },
    submit(){
        axios.post('/your-url', {name: this.name})
        try {
            // if (this.item.title == this.title)
            //     return true;
        } catch (error) {
            console.log(error);
        }
      },
  },
}
</script>


<style scoped>
.image h2 {
  font-style: italic;
}

/* Masonry */
*,
*:before,
*:after {
  box-sizing: inherit;
}

.image-gallery {
  column-gap: 1.5em;
}

.image {
  margin: 0 0 1.5em;
  display: inline-block;
  width: 100%;
}

.image img {
  width: 100%;
}

/* Masonry on large screens */
@media only screen and (min-width: 1024px) {
  .image-gallery {
    column-count: 4;
  }
}

/* Masonry on medium-sized screens */
@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .image-gallery {
    column-count: 3;
  }
}

/* Masonry on small screens */
@media only screen and (max-width: 767px) and (min-width: 540px) {
  .image-gallery {
    column-count: 2;
  }
}
</style>