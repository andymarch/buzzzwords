<template>
  <v-app>
    
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-btn
        href="https://github.com/andymarch"
        target="_blank"
        text
      >
        <span class="mr-2">Buzzzwords</span>
      </v-btn>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/andymarch/buzzzwords"
        target="_blank"
        text
      >
        <span class="mr-2">View Code</span>
        <v-icon>mdi-github</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
        <v-row
              align="center"
              justify="center"
            >
            <v-sheet>
              Are you going into hour five of a meeting that should have been a document?
            </v-sheet>
        </v-row>

      <BingoCard :words="wordlist"/>
      <v-row>
            <v-sheet>
              <h2>Why do you need access to my microphone?</h2>
              <div class="blurb-text">Buzzzwords uses your microphone to listen to the meeting and fill complete your card as it hears the words.
              Pressing the mute button above stops the recognition. Remember that you can disallow microphone access through your browser at any time.
              </div>
            </v-sheet>
        </v-row>
    </v-content>
  </v-app>
</template>

<script>
import BingoCard from './components/BingoCard'

export default {
  name: 'App',

  components: {
    BingoCard,
  },

  data: () => ({
    wordlist:[
      "context", "workflow", "behavioural", "platform", "scalable", 
      "real time", "empower", "simplify", "low code", "machine learning",
      "insights", "cyber", "automated", "threats", "business process",
      "seamless", "actionable", "advanced", "accelerate", "modern",
      "sophisticated", "flexible","robust", "comprehensive"]
  }),
};
</script>
