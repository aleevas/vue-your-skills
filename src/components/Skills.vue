<template>
  <div class="hello">
    <h1>{{name}}</h1>
    <ul>
     <li v-for="(value, index) in skills" :key='index'>
       {{index}} . {{value.skill}}
     </li>
    </ul>
    <button v-on:click="ChangeName" v-bind:disabled="btnState">{{btnName}}</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      name: "First name",
      btnName: "Change",
      btnState: true,
      skills: [
        {'skill': 'First skill'},
        {'skill': 'Second skill'}
      ]
    }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../css/skills.css"></style>
