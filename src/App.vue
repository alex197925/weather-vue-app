<!-- @format -->
<template>
  <div class="wrapper">
    <h1>Weather App</h1>
    <p>Weather in your {{ city == "" ? "city" : cityName }}</p>
    <input v-model="city" type="text" placeholder="City..." />
    <button @click="getWeather" v-if="city !== ''">Get Weather</button>
    <button disabled v-else>Type your city !</button>
    <p class="error">{{ error }}</p>
    <p v-show="info != null">{{ info.main.temp }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      city: "",
      error: "",
      info: null,
    };
  },

  methods: {
    getWeather() {
      if (this.city.trim().length < 2) {
        this.error = "City name have to be longer!!";
        return false;
      }
      this.error = "";
      axios
        .get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=2d8027559ee4c08ed99ff31fa9fb7e6e`
        )
        .then((res) => (this.info = res.data));
    },
  },

  computed: {
    cityName() {
      return " < " + this.city + " > ";
    },
  },
};
</script>

<style scoped>
.error {
  color: red;
}
.wrapper {
  width: 900px;
  height: 500px;
  padding: 20px;
  text-align: center;
  color: #fff;
  border-radius: 50px;
  background-color: #621022;
}

.wrapper h1 {
  margin-top: 50px;
  letter-spacing: 1px;
}

.wrapper p {
  padding-top: 20px;
  letter-spacing: 1px;
}

.wrapper input {
  margin-top: 30px;
  padding: 5px 8px;
  background: transparent;
  border: 0;
  border-bottom: 2px solid #370202;
  color: #fcfcfc;
  font-size: 14px;
  outline: none;
}

.wrapper button:disabled {
  background: #5a4202;
  border: 2px solid rgb(238, 141, 106);
  cursor: not-allowed;
}

.wrapper input:focus {
  border-bottom-color: #e3bc4d;
}

.wrapper button {
  background: #e3bc4d;
  color: #fff;
  border-radius: 10px;
  border: 2px solid #b99935;
  padding: 10px 15px;
  margin-left: 20px;
  cursor: pointer;
  border: none;
  transition: transform 500ms ease;
}

.wrapper button:hover {
  transform: scale(1.1) translateY(-5px);
}
</style>

API_key = "2d8027559ee4c08ed99ff31fa9fb7e6e"
