<template>
  <div class="flex justify-start flex-col items-center bg-black h-auto">
    <img class="w-56" src="../assets/star-wars-logo.jpg" alt="trooper" />
    <div
      class="w-screen flex flex-col text-center"
      v-for="p in people"
      :key="p.id"
    >
      <h2 class="text-3xl text-yellow-400">{{ p.name }}</h2>
      <p class="text-white">
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
