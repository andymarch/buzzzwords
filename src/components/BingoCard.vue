<template>
  <v-container>
    <v-row
          align="center"
          justify="center"
        >
        <div>
            <v-chip id="0" class="ma-2" x-large v-on:click="toggleWord('0')">
                {{words[0]}}
            </v-chip>
            <v-chip id="1" class="ma-2" x-large v-on:click="toggleWord('1')">
                {{words[1]}}
            </v-chip>
            <v-chip id="2" class="ma-2" x-large v-on:click="toggleWord('2')">
                {{words[2]}}
            </v-chip>
            <v-chip id="3" class="ma-2" x-large v-on:click="toggleWord('3')">
                {{words[3]}}
            </v-chip>
            <v-chip id="4" class="ma-2" x-large v-on:click="toggleWord('4')">
                {{words[4]}}
            </v-chip>
        </div>
        <div>
            <v-chip  id="5" class="ma-2" x-large v-on:click="toggleWord('5')">
                {{words[5]}}
            </v-chip>
            <v-chip  id="6" class="ma-2" x-large v-on:click="toggleWord('6')">
                {{words[6]}}
            </v-chip>
            <v-chip id="7" class="ma-2" x-large v-on:click="toggleWord('7')">
                {{words[7]}}
            </v-chip>
            <v-chip id="8" class="ma-2" x-large v-on:click="toggleWord('8')">
                {{words[8]}}
            </v-chip>
            <v-chip id="9" class="ma-2" x-large v-on:click="toggleWord('9')">
               {{words[9]}}
            </v-chip>
        </div>
        <div>
            <v-chip id="10" class="ma-2" x-large v-on:click="toggleWord('10')">
                {{words[10]}}
            </v-chip>
            <v-chip id="11" class="ma-2" x-large v-on:click="toggleWord('11')">
                {{words[11]}}
            </v-chip>
            <v-chip id="12" class="ma-2" x-large v-on:click="toggleWord('12')" >
                FREE
            </v-chip>
            <v-chip id="12" class="ma-2" x-large v-on:click="toggleWord('12')">
                {{words[12]}}
            </v-chip>
            <v-chip id="13" class="ma-2" x-large v-on:click="toggleWord('13')" >
                {{words[13]}}
            </v-chip>
        </div>
        <div>
            <v-chip id="14" class="ma-2" x-large v-on:click="toggleWord('14')">
               {{words[14]}}
            </v-chip>
            <v-chip id="15" class="ma-2" x-large v-on:click="toggleWord('15')">
                {{words[15]}}
            </v-chip>
            <v-chip id="16" class="ma-2" x-large v-on:click="toggleWord('16')">
                {{words[16]}}
            </v-chip>
            <v-chip id="17" class="ma-2" x-large v-on:click="toggleWord('17')">
                {{words[17]}}
            </v-chip>
            <v-chip id="18" class="ma-2" x-large v-on:click="toggleWord('18')">
                {{words[18]}}
            </v-chip>
        </div>
        <div>
            <v-chip id="19" class="ma-2" x-large v-on:click="toggleWord('19')">
                {{words[19]}}
            </v-chip>
            <v-chip id="20" class="ma-2" x-large v-on:click="toggleWord('20')">
                {{words[20]}}
            </v-chip>
            <v-chip id="21" class="ma-2" x-large v-on:click="toggleWord('21')" >
                {{words[21]}}
            </v-chip>
            <v-chip id="22" class="ma-2" x-large v-on:click="toggleWord('22')">
                {{words[22]}}
            </v-chip>
            <v-chip id="23" class="ma-2" x-large v-on:click="toggleWord('23')">
                {{words[23]}}
            </v-chip>
        </div>
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
  props: {
    words: Array
  },
  components:{
    RecognitionControl
  },
  data(){
  },
  methods:{
    updateCard(word){
       var index = this.words.indexOf(word)
       this.toggleWord(index)
    },
    toggleWord(location){
        var button = document.getElementById(location)
        if(button.classList.contains("red")){
            button.classList.remove("red")
        }
        else {
            button.classList.add("red");
        }
    }
  }
}
</script>

<style scoped>

</style>