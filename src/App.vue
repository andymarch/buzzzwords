<template>
  <v-app>
    <Logo/>
    <v-content>
      <v-container>
         <v-row class="blurb-row">
          <v-sheet>
            <div class="blurb-text">Is it a meeting or is it marketing?
            </div>
          </v-sheet>
        </v-row>
        <BingoCard class="gamepanel"/>
        <v-row class="blurb-row">
          <v-sheet>
            <h2>Why do you need access to my microphone?</h2>
            <div class="blurb-text">Buzzzwords uses your microphone to listen to the meeting and fill complete your card as it hears the words.
            Pressing the mute button above stops the recognition. Remember that you can disallow microphone access through your browser at any time.
            </div>
          </v-sheet>
        </v-row>
        <v-row class="blurb-row">
          <v-sheet>
            <h2>Are you listening to everything I say?</h2>
            <div class="blurb-text">All of the language processing is done using
               <a href="https://sdkcarlos.github.io/sites/artyom.html">Artyom.js</a> as a wrapper
               around the browser speech recongition API. For Chrome this uses 
               <a href="https://cloud.google.com/speech-to-text">Google's speech-to-text service</a>
                so while I'm not listening Google may be.
            </div>
          </v-sheet>
        </v-row>
        <v-row class="blurb-row">
          <v-sheet>
            <h2>Why doesn't speech recongition work?</h2>
            <div class="blurb-text">As with all language recognition problems; louder and slower :). If you are not running Chrome or Edge as a browser
              recongition will not work. This is because the voice recongition API is experimental. See the Mozilla compatibility table <a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition#Browser_compatibility">
              here</a>
            </div>
          </v-sheet>
        </v-row>
      </v-container>
    </v-content>
    <v-footer>
      <div>      
        <v-btn
          href="https://github.com/andymarch/buzzzwords"
          target="_blank"
          text
        >
        <span class="mr-2">GitHub</span>
        <v-icon>mdi-github</v-icon>
      </v-btn>
      </div>
      <v-spacer></v-spacer>
      <div>  
        <v-icon>
        mdi-code-tags
      </v-icon> <span class="ml-2">Hacked in quarantine by Andy March</span></div>
    </v-footer>
  </v-app>
</template>

<script>
import BingoCard from './components/BingoCard'
import Logo from './components/Logo'

export default {
  name: 'App',

  components: {
    BingoCard,
    Logo
  },

  data: () => ({
  
  }),
};
</script>
