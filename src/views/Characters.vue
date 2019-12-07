<template>
  <div class="flex justify-center flex-col items-center">
    <img class="w-56" src="../assets/star-wars-logo.jpg" alt="trooper" />
    <div class="w-100" v-for="p in people" :key="p.id">
      <h2 class="text-3xl">{{ p.name }}</h2>
      <p>
        Height: {{ p.height }}cm
        <br />
        Weight: {{ p.mass }}kg
        <br />
        Hair Color: {{ p.hair_color }}
        <br />
        Skin Color: {{ p.skin_color }}
        <br />
        Eye Color: {{ p.eye_color }}
        <br />
        Birth Year: {{ p.birth_year }}
        <br />
        Gender: {{ p.gender }}
        <br />
      </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  components: {},
  data() {
    return {
      people: []
    };
  },
  created() {
    axios
      .get("https://swapi.co/api/people/")
      .then(response => (this.people = response.data.results))

      .catch(error => console.log("error", error));
  }
};
</script>
