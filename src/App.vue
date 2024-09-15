<template>
  <div id="app">
    <div id="text">Selamat Docker Telah Berhasil Dibuat</div>
    <div class="additional-content">
      <h2>Docker Setup Sukses!</h2>
      <p>Ini adalah aplikasi Vue.js yang berjalan dalam container Docker.</p>
      <img src="./assets/logo.svg" alt="Vue.js Logo" class="logo" />
      <button @click="showRandomGif">Click Me</button>
      <div v-if="randomGifUrl" class="gif-container">
        <img :src="randomGifUrl" alt="Random GIF" class="random-gif" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      randomGifUrl: null, 
      gifUrls: [
        'https://media.giphy.com/media/ICOgUNjpvO0PC/giphy.gif',
        'https://media.giphy.com/media/jpVnC65DmYeyRL4LHS/giphy.gif',
        'https://media.giphy.com/media/l0HlDWEHz1V37m5Ek/giphy.gif',
        'https://media.giphy.com/media/3o7aD4p7sW45uTkF6g/giphy.gif',
        'https://media.giphy.com/media/xT9IgDEI1iZyb2wqo8/giphy.gif',
        'https://media.giphy.com/media/WsWuvZCICpsXPoYOM2/giphy.gif',
        'https://media.giphy.com/media/xUNd9FOSgUDmfVZ78I/giphy.gif',
        'https://media.giphy.com/media/wsUtUtLR3A2XPvfLVs/giphy.gif',
        'https://media.giphy.com/media/oFI7FttD0iC8V2Iqmy/giphy.gif',
        'https://media.giphy.com/media/SWzxAsBog0UxbnttYF/giphy.gif',
        'https://media.giphy.com/media/pPrUNsOY8CDS0/giphy.gif',
      ]
    };
  },
  methods: {
    showRandomGif() {
      const randomIndex = Math.floor(Math.random() * this.gifUrls.length);
      this.randomGifUrl = this.gifUrls[randomIndex]; 
    }
  }
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
  padding: 20px;
  box-sizing: border-box;
}

#text {
  font-size: 60px;
  color: rgb(0, 204, 255);
  text-align: center;
  margin-bottom: 20px;
}

.additional-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 600px;
}

.logo {
  width: 150px;
  margin-top: 20px;
  margin-bottom: 20px;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 16px;
  background-color: #42b983;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #2c8a6b;
}

p {
  font-size: 18px;
  color: #333;
  text-align: center;
  margin-top: 10px;
}

.gif-container {
  margin-top: 20px;
  text-align: center;
}

.random-gif {
  max-width: 100%;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

@media (max-width: 768px) {
  #text {
    font-size: 40px;
  }

  .additional-content {
    padding: 15px;
  }

  button {
    width: 100%;
  }
}
</style>
