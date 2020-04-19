<template>
  <div class="text-center" id="app"><br>
    <h1 style="color:green;">Language Translator</h1>
    <translatform v-on:submitform="translatetext"></translatform>
    <translateoutput v-text="translatedtext"></translateoutput>
  </div>
</template>

<script>
import translatform from './components/translatform' 
import translateoutput from './components/translateoutput' 

export default {
  name: 'app',
  components:{
    translatform,
    translateoutput,
  },
  data:function(){
    return{
      translatedtext:''
    }
  },
  
   methods: {
   translatetext:function(text,language) {
     this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200316T113721Z.e5174c119c9f27fd.2e0053c1a2ecf98d6f3431caf61f756287933205&lang='+language+'&text='+text)
     .then((response) => {
       
       this.translatedtext = response.body.text[0]
     })
   }
  }
}
</script>

<style>
 body{
   background:#2f3542;
 }
</style>
