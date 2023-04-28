<!-- @format -->
<template>
  <div class="wrapper">
    <h1>Weather App</h1>
    <p>Weather in your City</p>
    <input type="text" placeholder="City..." />
    <button>Get Weather</button>
  </div>
</template>

<script></script>

<style scoped>
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
