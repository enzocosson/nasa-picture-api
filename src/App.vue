<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

let data = ref("");

onMounted(async () => {
  const reponse = await axios.get(
    "https://api.nasa.gov/planetary/apod/?api_key=Tbw3lCgtQiaoMzflOUtOl9mLE9LD8SQ2LM70dy2r"
  );
  console.log(reponse.data);
  data.value = reponse.data;
});
</script>

<template>
  <div class="main">
    <h1>Astronomy Picture of the Day</h1>
    <div class="container_personnages">
      <h2>{{ data.title }}</h2>
      <div class="container_img">
        <img :src="data.hdurl" alt="" />
      </div>
      <h2>{{ data.date }}</h2>
      <p>{{ data.explanation }}</p>
    </div>

    <footer>
      <p>
        © 2023 - Enzo Cosson | <a href="https://api.nasa.gov/">API Source</a>
      </p>
    </footer>
  </div>
</template>

<style lang="scss" scoped>
.main {
  position: relative;
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  h1 {
    font-size: 5rem;
    text-align: center;
    font-weight: 700;
    color: var(--black);
    text-transform: uppercase;
    letter-spacing: 0.2rem;
    margin: 3rem;
  }
  .container_personnages {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    h2 {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--black);
      text-transform: uppercase;
      letter-spacing: 0.2rem;
      margin: 3rem;
    }
    .container_img {
      height: 80%;
      width: 80%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    img {
      height: 100%;
      width: 100%;
      object-fit: cover;

      border-radius: 10px;
      box-shadow: rgba(54, 54, 54, 0.74) 0px 2px 8px 0px;
    }
    p {
      font-size: 1.2rem;
      font-weight: 500;
      color: var(--black);
      letter-spacing: 0.2rem;
      margin: 3rem;
      width: 80%;
      text-align: justify;
    }
  }

  footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 3rem;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--black);
    p {
      font-size: 1rem;
      font-weight: 500;
      color: var(--white);
      letter-spacing: 0.2rem;
      margin: 3rem;
      width: 80%;
      text-align: center;

      a {
        color: rgb(136, 177, 252);
        text-decoration: none;
        font-weight: 500;
      }
    }
  }
}
</style>
