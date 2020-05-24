<template>
      <v-btn class="mx-2" fab dark large color="primary" v-on:click="toggleMic">
        <v-icon id="microphoneControl">{{recordIcon}}</v-icon>
    </v-btn>
</template>
<script>
import Artyom from "artyom.js"
export default {
    name: 'recognitionControl',
      props: {
        words: Array
    },
    beforeUpdate () {
        console.log('beforeUpdate:', this.words)
    },
    data(){
        return{
            recognition: undefined,
            recording:false,
            recordIcon: 'mdi-microphone-off'
        }
    },
    created(){
        this.recognition = new Artyom();
        this.words.forEach(element => {
            this.setWord(element)
        });

        this.recognition.initialize({
                lang:"en-GB",// A lot of languages are supported. Read the docs !
                continuous:true,// Artyom will listen forever
                listen:true, // Start recognizing
                debug:true, // Show everything in the console
                speed:1 // talk normally
            }).then(function(){
                console.log("Ready to work !");
            });
    },
    methods: {
        toggleMic(){
            if(!this.recording){
                this.recording = true
                this.start()
                this.recordIcon = 'mdi-microphone'
            }
            else{
                this.recording = false
                this.stop()
                this.recordIcon = 'mdi-microphone-off'
            }
        },
        start(){
            this.recognition.obey();
        },
        stop(){
            this.recognition.dontObey();
        },
        setWord(word){
            //setting parent is a hack to put context in the action
            //there is definately a better way to do this
            const parent = this
            var command = {
                indexes:[word],
                action:function(){
                    parent.wordMatched(word)
                }
            };

            this.recognition.addCommands(command);
            console.log("added "+word)
        },
        wordMatched(word){
            this.$emit("buzz",word)
        }
    }
}
</script>
<style scoped>
</style>