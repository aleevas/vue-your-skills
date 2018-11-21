<template>
  <div class="container">
    <div class="holder">
      <h1>{{title}}</h1>
      <ul>
        <li v-for="(value, index) in skills" :key='index'>
          {{index}} . {{value.skill}}
        </li>
      </ul>
      <button v-on:click="ChangeName" v-bind:disabled="btnState">{{btnName}}</button>
      <!-- <div v-bind:style="{backgroundColor:bgColor,with: bgWith, height: bgHeight, marginTop: bgMarginTop}"> -->
          <p>These are the skills that you possess.</p>
      <!-- </div> -->
      </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      title: "My title",
      btnName: "Change",
      btnState: true,
      skills: [
        {'skill': 'First skill'},
        {'skill': 'Second skill'}
      ],
      bgColor: 'lightgrey',
      bgWith: '100%',
      bgHeight: '25px',
      bgMarginTop: '25px',
    }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../css/skills.css"></style>
