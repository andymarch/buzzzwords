<template>
  <v-container>
    <v-row
          align="center"
          justify="center"
        >
        <v-container>
            <v-row>
                <v-spacer/>
                <v-col class="wordcell" id="0" v-on:click="toggleWord('0')">
                    {{words[0]}}
                </v-col>
                <v-col class="wordcell" id="1" v-on:click="toggleWord('1')">
                    {{words[1]}}
                </v-col>
                <v-col class="wordcell" id="2" v-on:click="toggleWord('2')">
                    {{words[2]}}
                </v-col>
                <v-col class="wordcell" id="3" v-on:click="toggleWord('3')">
                    {{words[3]}}
                </v-col>
                <v-col class="wordcell" id="4" v-on:click="toggleWord('4')">
                    {{words[4]}}
                </v-col>
                <v-spacer/>
            </v-row>
            <v-row>
                <v-spacer/>
                <v-col class="wordcell" id="5" v-on:click="toggleWord('5')">
                    {{words[5]}}
                </v-col>
                <v-col class="wordcell" id="6" v-on:click="toggleWord('6')">
                    {{words[6]}}
                </v-col>
                <v-col class="wordcell" id="7" v-on:click="toggleWord('7')">
                    {{words[7]}}
                </v-col>
                <v-col class="wordcell" id="8" v-on:click="toggleWord('8')">
                    {{words[8]}}
                </v-col>
                <v-col class="wordcell" id="9" v-on:click="toggleWord('9')">
                    {{words[9]}}
                </v-col>
                <v-spacer/>
            </v-row>
            <v-row>
                <v-spacer/>
                <v-col class="wordcell" id="10" v-on:click="toggleWord('10')">
                    {{words[10]}}
                </v-col>
                <v-col class="wordcell" id="11" v-on:click="toggleWord('11')">
                    {{words[11]}}
                </v-col>
                <v-col class="toggled">
                    FREE
                </v-col>
                <v-col class="wordcell" id="12" v-on:click="toggleWord('12')">
                    {{words[12]}}
                </v-col>
                <v-col class="wordcell" id="13" v-on:click="toggleWord('13')">
                    {{words[13]}}
                </v-col>
                <v-spacer/>
            </v-row>
            <v-row>
                <v-spacer/>
                <v-col class="wordcell" id="14" v-on:click="toggleWord('14')">
                    {{words[14]}}
                </v-col>
                <v-col class="wordcell" id="15" v-on:click="toggleWord('15')">
                    {{words[15]}}
                </v-col>
                <v-col class="wordcell" id="16" v-on:click="toggleWord('16')">
                    {{words[16]}}
                </v-col>
                <v-col class="wordcell" id="17" v-on:click="toggleWord('17')">
                    {{words[17]}}
                </v-col>
                <v-col class="wordcell" id="18" v-on:click="toggleWord('18')">
                    {{words[18]}}
                </v-col>
                <v-spacer/>
            </v-row>
            <v-row>
                <v-spacer/>
                <v-col class="wordcell" id="19" v-on:click="toggleWord('19')">
                    {{words[19]}}
                </v-col>
                <v-col class="wordcell" id="20" v-on:click="toggleWord('20')">
                    {{words[20]}}
                </v-col>
                <v-col class="wordcell" id="21" v-on:click="toggleWord('21')">
                    {{words[21]}}
                </v-col>
                <v-col class="wordcell" id="22" v-on:click="toggleWord('22')">
                    {{words[22]}}
                </v-col>
                <v-col class="wordcell" id="23" v-on:click="toggleWord('23')">
                    {{words[23]}}
                </v-col>
                <v-spacer/>
            </v-row>
        </v-container>
    </v-row>
    <v-row align="center" justify="center">
    <RecognitionControl v-on:buzz="updateCard" :words="words"/>
    </v-row>
  </v-container>
</template>
<script>
import RecognitionControl from './RecognitionControl'
export default {
  name: 'BingoCard',
  data() {
      return{
          words:this.shuffle([
      "context", "workflow", "behavioural", "platform", "scalable", 
      "real time", "empower", "simplify", "low code", "machine learning",
      "insights", "cyber", "automated", "threats", "business process",
      "seamless", "actionable", "advanced", "accelerate", "modern",
      "sophisticated", "flexible","robust", "comprehensive"])
      }
  },
  components:{
    RecognitionControl
  },
  methods:{
    shuffle(array) {
    var currentIndex = array.length, temporaryValue, randomIndex;

    // While there remain elements to shuffle...
    while (0 !== currentIndex) {

        // Pick a remaining element...
        randomIndex = Math.floor(Math.random() * currentIndex);
        currentIndex -= 1;

        // And swap it with the current element.
        temporaryValue = array[currentIndex];
        array[currentIndex] = array[randomIndex];
        array[randomIndex] = temporaryValue;
    }

    return array;
    },
    updateCard(word){
       var index = this.words.indexOf(word)
       this.toggleWord(index)
    },
    toggleWord(location){
        var button = document.getElementById(location)
        if(button.classList.contains("toggled")){
            button.classList.remove("toggled")
        }
        else {
            button.classList.add("toggled");
        }
    }
  }
}
</script>

<style scoped>

</style>