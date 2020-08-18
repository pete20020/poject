<template>
  <div class="hello">
    <p>{{msg}}</p>
    <button @click="downFunction" class="btn btn-info">{{ label }}กดเลือกตัว</button>
    <button @click="upFunction" class="btn btn-info">{{ label }}</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function () {
    return {
      counter: 0,
      fsize: 50,
    };
  },
  randomDamage: 0,
  player: [
    { name: "Omen", hp: 150, image: "600px-Omen_Artwork.png" },
    { name: "Jett", hp: 125, image: "Jett_Artwork.png" },
    { name: "Viper", hp: 145, image: "Viper+Concept.png" },
    { name: "Breach", hp: 155, image: "V_AGENTS_587x900_Breach.png" },
  ],

  monster: [
    { name: "csgo1", hp: 35, image: "csgo1.jpg" },
    { name: "csgo2", hp: 70, image: "csgo2.jpg" },
    { name: "boss", hp: 140, image: "agent-cypher.png" },
  ],

  props: {
    //label: string,
  },
  methods: {
  
    randomDamage: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    upFunction: function () {
      this.counter += 1;
      this.fsize += 10;

      this.Semit("cc", this.counter);
    },
    downFunction: function () {
      this.counter -= 1;
      this.fsize -= 10;
      console.log(this.fsize);
      console.log(this.counter);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>