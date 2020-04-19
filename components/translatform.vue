<template>
 <div class="container" id="translatform">
  <!-- <div class="row"> -->
    <div class="card text-center" style="background-color:#57606f;">
  <div class="card-header" style="height:8rem;">
    <form id="transform" class="well" v-on:submit="submitform">
        <input class="form-control" type="text" v-model="text2translate" placeholder="Enter a Word">
        <select class="form-control" v-model="language">
          <option value="ar">Arabic</option>
          <option value="bn">Bengali</option>
          <option value="zh">chinese</option>
          <option value="da">Danish</option>
          <option value="nl">Dutch</option>
          <option value="en">English</option>
          <option value="fr">French</option>
           <option value="de">German</option>
          <option value="el">Greek</option>
          <option value="gu">Gujrati</option>
          <option value="he">Hebrew</option>
          <option value="hi">Hindi</option>
          <option value="is">Icelandic</option>
          <option value="id">Indonesian</option>
          <option value="ga">Irsh</option>
          <option value="it">Italian</option>
          <option value="ja">Japanese</option>
          <option value="ko">Korean</option>
          <option value="la">Latin</option>
          <option value="ml">Malayalam</option>
          <option value="mr">Marathi</option>
          <option value="no">Norwegian</option>
          <option value="pa">Punjabi</option>
          <option value="fa">Persian</option>
          <option value="pt">Portuguese</option>
          <option value="ru">Russian</option>
          <option value="es">Spanish</option>
          <option value="sv">Swedish</option>
          <option value="ta">Tamil</option>
          <option value="te">Telugu</option>
          <option value="tr">Turkish</option>
          <option value="ur">Urdu</option>
         </select>
        <input class="btn btn-primary" type="submit" value="Translate">
      </form>
  </div>
    
    </div>
 </div>
</template>

<script>
 

export default {
  name: 'translatform',
  data(){
      return{
          text2translate:'',
          language:'',
      }
  },
  created(){
    this.language ='ru'
  },
  methods:{
    submitform(e){
        this.$emit('submitform',this.text2translate,this.language)
        e.preventDefault();
    }
  }
  }

</script>

<style>
#transform{
    border-radius: 10px;
    border:1px #ccc solid;
}
</style>
