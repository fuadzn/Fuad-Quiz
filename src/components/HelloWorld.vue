<template>
  <div class="hello">
    <h1 v-if="show">{{ msg }}</h1>
    <h1 v-else>Judul Disembunyikan</h1>
    
    <p>{{ nama }}</p>

    <input type="text" v-model="nama">

    <button type="button" v-on:click="hideTitle">Click Me</button>
    <br>
    <h3>Jawaban Benar : {{score}}</h3>
    <li v-for="question1 in question1">
      <h3>{{question1}}</h3>
      <answer1 v-for="answer1 in answer1">
        <br>
        <input type="radio" v-on:click="increment" value="A. Depok">
        {{answer1}}
      </answer1>
      <answer2 v-for="answer2 in answer2">
        <br>
        <input type="radio" v-on:click="increment" value="B. Bandung">
        {{answer2}}
      </answer2>
      <answer3 v-for="answer3 in answer3">
        <br>
        <input type="radio" v-on:click="increment" value="C. Garut">
        {{answer3}}
      </answer3>
    </li>
    <br>
    <li v-for="question2 in question2">
      <h3>{{question2}}</h3>
      <answer4 v-for="answer4 in answer4">
        <br>
        <input type="radio" v-on:click="increment" value="A. Rekayasa Perangkat Lunak">
        {{answer4}}
      </answer4>
      <answer5 v-for="answer5 in answer5">
        <br>
        <input type="radio" v-on:click="increment" value="B. Audio Video">
        {{answer5}}
      </answer5>
      <answer6 v-for="answer6 in answer6">
        <br>
        <input type="radio" v-on:click="increment" value="C. Tataboga">
        {{answer6}}
      </answer6>
    </li>
    <br>
    <li v-for="question3 in question3">
      <h3>{{question3}}</h3>
      <answer7 v-for="answer7 in answer7">
        <br>
        <input type="radio" v-on:click="increment" value="A. Suzuki">
        {{answer7}}
      </answer7>
      <answer8 v-for="answer8 in answer8">
        <br>
        <input type="radio" v-on:click="increment" value="B. Lenovo">
        {{answer8}}
      </answer8>
      <answer9 v-for="answer9 in answer9">
        <br>
        <input type="radio" v-on:click="increment" value="C. Honda">
        {{answer9}}
      </answer9>
    </li>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function(){
    return {
      nama: 'Fuad',
      show: true,
      score: 0,
      question1    : ['1. Apa ibukota Jawa Barat'],
      answer1      : ['A. Depok'],
      answer2      : ['B. Bandung'],
      answer3      : ['C. Garut'],
      question2    : ['2. Jurusan apa saja yang ada di SMKN 4 Bandung, kecuali'],
      answer4      : ['A. Rekayasa Perangkat Lunak'],
      answer5      : ['B. Audio Video'],
      answer6      : ['C. Tataboga'],
      question3    : ['Salah satu brand laptop yaitu'],
      answer7      : ['A. Suzuki'],
      answer8      : ['B. Lenovo'],
      answer9      : ['C. Honda'],
    }
  },
  methods: {
    hideTitle () {
      this.show = !this.show
    },
    increment () {
      var value = event.target.value;
      if  (value === "B. Bandung"){
        this.score++;
      }else if  (value === "C. Tataboga"){
        this.score++;
      }else if  (value === "B. Lenovo"){
        this.score++;
      }else{
        this.score--;
      }
    }
  },
  mounted: function () {
    this.nama = 'Zaidan'
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
