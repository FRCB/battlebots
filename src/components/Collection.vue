<template>
    <div class = 'collection'>
        <div class='top'>
        <p>Bot #1: {{ bot1? bot1 : "Select a bot below"}}</p>
        <p>Bot #2: {{ bot2? bot2 : "Select a bot below"}}</p>
        <button @click='battle'>Battle</button>
        <button @click='clearBattle'>Clear</button>
        <br>
        </div>

        <br>

        <div class='botgroup'>

            <div class = 'robot' v-for='(bot, i) in botgroup' :key='i' >
                <h4>{{bot.botName}}</h4>
                <p>Attack: {{bot.attackVal}}</p>
                <p>Health: {{bot.healthVal}}</p>
                <br>
                <button @click='selectBot(bot.botName)' >Select</button>
                <button @click='retireBot(i)' >Retire</button>
                <br>
            </div>
            <br>
        </div>
  </div>
</template>

<script>
export default {
  props: ["botgroup"],

  data() {
    return {
      bot1: "",
      bot2: ""
    };
  },

  methods: {
    selectBot(bot) {
      if (!this.bot1) {
        this.bot1 = bot;
      } else if (this.bot1 && !this.bot2) {
        this.bot2 = bot;
      }
    },
    retireBot(i) {
      this.botgroup.splice(i);
    },
    clearBattle() {
      this.bot1 = "";
      this.bot2 = "";
    },
    battle() {
      let num1 = Math.random();
      let num2 = Math.random();

      if (num1 > num2) {
        alert(this.bot1 + " " + "wins");
      } else {
        alert(this.bot2 + " " + "wins");
      }
    }
  }
};
</script>

<style scoped>
.collection {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.top {
  border-bottom: solid grey 1px;
  display: flex;
  flex-direction: column;
}

p {
  font-family: Arial;
  margin: 6px;
}
h4 {
  font-family: Arial;
}
.robot {
  display: flex;
  flex-direction: column;
  align-items: center;
  align-content: center;
  border: solid grey 1px;
  width: 200px;
}

.botgroup {
  display: flex;
}
</style>