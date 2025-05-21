<template>
  <div class="video-container">
    <video autoplay muted loop class="video-background">
      <source :src="videoUrl" type="video/mp4">
    </video>
    <div class="message-overlay">
      <h1>🏀 {{ message }} 🏀</h1>
      <h2>From: {{ messageFrom }}</h2>
      <h2>To: {{ messageTo }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      messageTo: 'All-Star Student',
      messageFrom: 'Your Biggest Fan',
      message: "Slam dunk this academic year!",
      videoUrl: "https://assets.mixkit.co/videos/preview/mixkit-man-playing-basketball-558-large.mp4"
    }
  }
}
</script>

<style>
body, html {
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.video-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.video-background {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: 1;
  object-fit: cover;
}

.message-overlay {
  position: relative;
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.7);
  padding: 2rem;
  border-radius: 15px;
  color: white;
  text-align: center;
  max-width: 80%;
  margin: 0 auto;
  border: 3px solid #ff6b00;
  text-shadow: 2px 2px 4px #000;
}

h1 {
  font-size: 2.5rem;
  color: #ffcc00;
  margin-bottom: 1rem;
}

h2 {
  font-size: 1.8rem;
  margin: 0.8rem 0;
}

/* Basketball animation */
h1::before, h1::after {
  content: "🏀";
  display: inline-block;
  animation: bounce 0.5s infinite alternate;
}

@keyframes bounce {
  from { transform: translateY(0); }
  to { transform: translateY(-10px); }
}
</style>