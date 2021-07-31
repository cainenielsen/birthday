<template>
  <div id="canvas" :style="`background-image: ${randomZags()}`">
    <h1>
      <span
        :style="`color: ${getRandomColor()};`"
        v-for="(u, i) in msgArr(this.message)"
        :key="i"
      >
        <b>{{ u.char }}</b>
      </span>
      <span v-if="$route.params.name">
<span
        :style="`color: ${getRandomColor()};`"
        v-for="(u, i) in msgArr(`, ${$route.params.name}`)"
        :key="i"
      >
        <b>{{ u.char }}</b>
      </span>
      </span>
    </h1>
    <p>
      <span
        :style="`color: ${getRandomColor()};`"
        v-for="(u, i) in msgArr(`${getRandomQuote()}`)"
        :key="i"
      >
        <b>{{ u.char }}</b>
      </span>
    </p>

    <button :style="`color: ${getRandomColor()};`" @click="doSomething"><i class="fas fa-gift"></i></button>
  </div>
</template>

<script>
import confetti from 'canvas-confetti';

export default {
  data() {
    return {
      message: "Happy Birthday",
      subMessage: "Yeah dude, it is your birthday!",
      subMessages: [
        "One time for the birthday b****.",
        "Two times for the birthday b****.",
        "You're old now...",
        "Welcome to adulting.",
        "Eat some cake.",
        "Noodle",
        "Did you bring your suit?",
        "It's totally wicked!",
        "A ripe old age...",
        "I want to get chocolate wasted.",
        "Pickle",
        "Get yourself somethin' real nice clark.",
        "Run forrest, RUN!",
        "Beauler... beauler...",
        "Take the day off!",
        "What do you get a hunter for his birthday? A birthday pheasant.",
        "What does a clam do on his birthday? He shellabrates!",
        "When I was born I was so surprised, I didn’t talk for a year and a half.",
        "What sort of birthday cake do ghosts prefer? An 'I scream' cake.",
        "You know you're getting old when you go to an antique auction and three people bid on you.",
        "FR E SH A VOCA DO",
        "I need wine",
        "Honey, where are my pants?",
        "One does not simply 'have a birthday'",
        "Why is the rum gone?",
        "I'm gonna need to ask you to come in on Saturday, that'd be great.",
        "It only comes once a year",
        "Stay gangster!",
        "I can't wait to be less than 6 feet away from you! Happy birthday!",
        "Happy Birthday! Don't forget to iron that birthday suit.",
        "Those aren't gray hairs that you see. They're strands of birthday glitter growing out of your head.",
        "Don't let aging get you down. It's too hard to get up again!",
        "Q: What goes up and never comes down? A: Your age!",
        ""
      ],
      palletes: [
        ["#EFB0C9", "#F4C2D7", "#F8DAE9", "#B9D6F3", "#A1C9F1", "#F1E8D9"]
      ]
    };
  },
  methods: {
    doSomething() {
      confetti({
        particleCount: 100,
        spread: 70,
        origin: { y: 0.6 }
      });
    },
    getRandomColor() {
      return this.palletes[0][
        Math.floor(Math.random() * this.palletes[0].length)
      ];
    },
    getRandomQuote() {
      return this.subMessages[
        Math.floor(Math.random() * this.subMessages.length)
      ];
    },
    randomZags() {
      return `linear-gradient(135deg, ${this.getRandomColor()} 25%, transparent 25%), linear-gradient(225deg, ${this.getRandomColor()} 25%, transparent 25%), linear-gradient(45deg, ${this.getRandomColor()} 25%, transparent 25%), linear-gradient(315deg, ${this.getRandomColor()} 25%, ${this.getRandomColor()} 5%);`;
    },
    msgArr(message) {
      var units = [];
      message.split("").forEach((u) => {
        units.push({ char: u, color: this.getRandomColor });
      });
      return units;
    }
  }
};
</script>

<style>
#app {
  padding: 0px;
  margin: 0px;
  background-color: #e5e5f7;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

#canvas {
  font-family: sans-serif;
  text-align: center;
  opacity: 1;
  background-position: 40px 0, 40px 0, 0 0, 0 0;
  background-size: 80px 80px;
  background-repeat: repeat;
  height: 100vh;
  width: 100vw;
  overflow-x: hidden;
  box-sizing: border-box;
}

body {
  padding: 0px;
  margin: 0px;
  background-color: #e5e5f7;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

a,
button {
  background: none;
  border: none;
  font-size: 25vw;
  box-shadow: 0px 3px 0px #b2a98f, 0px 14px 10px rgba(0, 0, 0, 0.15),
    0px 24px 2px rgba(0, 0, 0, 0.1), 0px 24px 30px rgba(0, 0, 0, 0.1);
  -webkit-text-stroke: 1px grey;
  font-size: 25vw;
  filter: saturate(200%);
  font-weight: bolder;
  background-color: white;
  border-radius: 10%;
  aspect-ratio: 1/1;
  cursor: pointer;
  padding: 1vw;
  line-height: 0;
  animation: shake 0.5s;

  /* When the animation is finished, start again */
  animation-iteration-count: infinite;
}

h1 {
  font-size: 18vw;
  text-shadow: 0px 3px 0px #b2a98f, 0px 14px 10px rgba(0, 0, 0, 0.15),
    0px 24px 2px rgba(0, 0, 0, 0.1), 0px 24px 30px rgba(0, 0, 0, 0.1);
  -webkit-text-stroke: 1px grey;
  filter: saturate(200%);
  font-weight: bolder;
  text-transform: capitalize;
}

p {
  text-shadow: 0px 3px 0px #b2a98f, 0px 14px 10px rgba(0, 0, 0, 0.15),
    0px 24px 2px rgba(0, 0, 0, 0.1), 0px 24px 30px rgba(0, 0, 0, 0.1);
  -webkit-text-stroke: 1px grey;
  font-size: 8vw;
  filter: saturate(200%);
  font-weight: bolder;
  margin-left: 8vh;
  margin-right: 8vh;
  line-height: 1.5em;
}

@media only screen and (orientation: landscape) {
  h1 {
    font-size: 7vw;
  }

  button {
    font-size: 10vw;
  }
  p {
    font-size: 2.5vw;
  }
  #canvas {
    padding-left: 20vw;
    padding-right: 20vw;
  }
}

@keyframes shake {
  0% { transform: translate(1px, 1px) rotate(0deg); }
  10% { transform: translate(-1px, -2px) rotate(-1deg); }
  20% { transform: translate(-3px, 0px) rotate(1deg); }
  30% { transform: translate(3px, 2px) rotate(0deg); }
  40% { transform: translate(1px, -1px) rotate(1deg); }
  50% { transform: translate(-1px, 2px) rotate(-1deg); }
  60% { transform: translate(-3px, 1px) rotate(0deg); }
  70% { transform: translate(3px, 1px) rotate(-1deg); }
  80% { transform: translate(-1px, -1px) rotate(1deg); }
  90% { transform: translate(1px, 2px) rotate(0deg); }
  100% { transform: translate(1px, -2px) rotate(-1deg); }
}
</style>
