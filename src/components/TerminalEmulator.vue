<template>
  <div class="terminal">
    <div class="terminal-header">
      <div class="buttons">
        <div class="close"></div>
        <div class="minimize"></div>
        <div class="expand"></div>
      </div>
      <div class="qdrx">🏠qdrx</div>
      •••
    </div>
    <div class="terminal-body">
      <div class="terminal-content">
        <p v-if="showText" class="typed-text" :class="{ 'hide-cursor': !showCursor }" v-html="displayText"></p>
        <div class="terminal-input-wrapper">
          <div class="input-container">
            <input v-model="command" @keydown.enter="onCommandInput" :size="command.length || 15" class="terminal-input" type="text" placeholder="Enter commands">
          </div>
          <span v-if="showCursor" class="cursor">❚</span>
        </div>
      </div>
    </div>

  </div>
</template>
  
<script>
export default {
  name: 'TerminalEmulator',
  data() {
    return {
      text: [
        `▲ ~ echo Hi! My name is Ihor. As a person, I am sociable, friendly, diligent and curious about programming.\n▲ ~ echo My diverse project portfolio includes a Film Matching App, Discord Accounts Manager, and BookAI, showcasing skills in NodeJS, TypeScript, Express, Nest.js, Redis, PostgreSQL, and more.`,
      ],
      currentText: '',
      displayText: '',
      currentIndex: 0,
      showText: true,
      showCursor: false,
      command: '',
    };
  },
  mounted() {
    this.animateText();
  },
  methods: {
    typeCharacter(char) {
      return new Promise(resolve => {
        setTimeout(() => {
          resolve(char);
        }, 10);
      });
    },
    async animateText() {
      for (const char of this.text[this.currentIndex]) {
        const nextChar = await this.typeCharacter(char);
        this.currentText += nextChar;
        this.displayText = this.currentText;
      }
      this.showCursor = true;
    },
    onCommandInput(event) {
      this.command = event.target.value;
      this.processCommand();
    },
    processCommand() {
      if (this.command === 'echo') {
        this.displayText = 'Echo command received!';
      } else {
        this.displayText = 'Unknown command: ' + this.command;
      }
      this.command = '';
    },
  }
};
</script>
  
  
<style scoped>
.qdrx {
  font-size: 1em;
  margin-right: 50px;
  flex-grow: 1;
  text-align: center;
}

.terminal {
  font-family: 'Avenir Next', monospace;
  background-color: #282a36;
  color: #f8f8f2;
  border-radius: 5px;
  width: 70%;
  max-width: 800px;
  margin: 20px auto;
  height: 250px;
  overflow: hidden;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

@media (max-width: 768px) {
  .terminal {
    width: 95%;
    font-size: 0.8em;
  }
}

.terminal-header {
  color: #f8f8f2;
  padding: 8px 12px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.terminal-header .buttons {
  display: flex;
  gap: 8px;
}

.terminal-header .buttons div {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.terminal-header .close {
  background-color: #ff5555;
}

.terminal-header .minimize {
  background-color: #f1fa8c;
}

.terminal-header .expand {
  background-color: #50fa7b;
}

.terminal-body {
  padding: 12px;
}

.terminal-content {
  white-space: pre-wrap;
  line-height: 1.6;
}

.typed-text.hide-cursor::after {
  color: #ff79c6;
  content: '❚';
  animation: blink 1s step-end infinite;
}

.terminal-input-wrapper {
  display: flex;
  align-items: center;
  padding: 10px;
}

.terminal-input {
  font-family: 'Avenir Next', monospace;
  font-size: 16px;
  background: transparent;
  border: none;
  color: #fff;
  caret-color: transparent;
  outline: none;
  width: 100%;
}

.terminal-input::after {
  color: #ff79c6;
  content: '❚';
  animation: blink 1s step-end infinite;
}

.cursor {
  display: flex;
  color: #ff79c6;
  animation: blink 1s step-end infinite;
}


@keyframes blink {
  50% {
    opacity: 0;
  }
}
</style>
  