
<template>
  <div class="traffic-light-container d-flex justify-content-center align-items-center">
    <div class="button-container me-3 d-flex flex-column justify-content-center">
      <button type="button" class="btn btn-red mb-2" @click="Cambiar">Rojo</button>
      <button type="button" class="btn btn-yellow mb-2" @click="Cambiar2">Amarillo</button>
      <button type="button" class="btn btn-green mb-2" @click="Cambiar3">Verde</button>
    </div>

    <div class="traffic-light">
      <rojo :isOn="isRedLightOn" />
      <amarillo :isOn="isYellowLightOn" />
      <verde :isOn="isGreenLightOn" />
    </div>
  </div>
</template>

<script>
import rojo from './components/rojo.vue';
import amarillo from './components/amarillo.vue';
import verde from './components/verde.vue';

export default {
  components: {
    rojo,
    amarillo,
    verde,
  },
  data() {
    return {
      isRedLightOn: false,
      isYellowLightOn: false,
      isGreenLightOn: false,
    };
  },
  methods: {
    Cambiar() {
      this.isRedLightOn = true;
      this.isYellowLightOn = false;
      this.isGreenLightOn = false;
    },
    Cambiar2() {
      this.isRedLightOn = false;
      this.isYellowLightOn = true;
      this.isGreenLightOn = false;
    },
    Cambiar3() {
      this.isRedLightOn = false;
      this.isYellowLightOn = false;
      this.isGreenLightOn = true;
    },
  },
};
</script>

<style scoped>
html, body {
  height: 100%; 
  margin: 0; 
  background: linear-gradient(135deg, #ff7e5f, #feb47b);
  font-family: Arial, sans-serif; 
}

.traffic-light-container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.button-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
  align-items: flex-end;
  margin-right: 15px; 
}

.btn {
  width: 120px; 
  padding: 10px;
  font-size: 16px;
  font-weight: bold;
  border: none;
  border-radius: 25px; 
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease; 
}

.btn-red {
  background-color: #e74c3c; 
  color: white;
  box-shadow: 0 4px 8px rgba(231, 76, 60, 0.3); 
}

.btn-red:hover {
  background-color: #c0392b; 
}

.btn-yellow {
  background-color: #f1c40f;
  color: white;
  box-shadow: 0 4px 8px rgba(241, 196, 15, 0.3);
}

.btn-yellow:hover {
  background-color: #f39c12;
}

.btn-green {
  background-color: #2ecc71;
  color: white;
  box-shadow: 0 4px 8px rgba(46, 204, 113, 0.3);
}

.btn-green:hover {
  background-color: #27ae60;
}

.traffic-light {
  width: 140px;
  background: linear-gradient(145deg, #333, #222);
  padding: 30px;
  border-radius: 30px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 400px;
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.6), inset 0px -3px 10px rgba(0, 0, 0, 0.7);
  border: 2px solid #444;
}

.light {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background-color: #555;
  opacity: 0.3;
  transition: opacity 0.3s ease, box-shadow 0.3s ease;
  box-shadow: inset 0px 0px 10px rgba(0, 0, 0, 0.5);
}

.light.on {
  opacity: 1;
  box-shadow: 0 0 15px 5px rgba(255, 255, 255, 0.5);
}

.red {
  background-color: #e74c3c;
}

.yellow {
  background-color: #f1c40f;
}

.green {
  background-color: #2ecc71;
}
</style>