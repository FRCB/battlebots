<template>
    <div class = 'create'>
        <input 
        placeholder='Bot Name'
        v-model='botName'
        type="text">
        <input 
        placeholder='Attack Value'
        v-model='attackVal'
        type="number">
        <input 
        placeholder='Health Value'
        v-model='healthVal'
        type="number">
    <div class='button'>
        <button @click='addNewBot(botName, attackVal, healthVal)'>Submit</button>
        <button @click='clearInput'>Clear</button>
    </div>
        <div>
            <h4>{{botName}}</h4>
            <p>{{attackVal}}</p>
            <p>{{healthVal}}</p>
        </div>
  </div>
</template>

<script>
export default {
  props: ["addNewBot"],

  data() {
    return {
      botName: "",
      attackVal: 0,
      healthVal: 0
    };
  },
  methods: {
    clearInput() {
      this.botName = "";
      this.attackVal = 0;
      this.healthVal = 0;
    }
  }
};
</script>

<style scoped>
.create {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: space-around;
  align-items: center;
  align-content: center;
  margin-top: 30px;
}
input {
  margin: 15px;
  height: 20px;
  width: 15%;
}
.button {
  display: flex;
  margin: 10px;
}
button {
  margin: 10px;
}
p {
  font-family: Arial;
}
h4 {
  font-family: Arial;
}
</style>