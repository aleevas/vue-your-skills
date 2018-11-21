<template>
  <div class="container">
    <div class="holder">
      <h1>{{title}}</h1>
      <form @submit.prevent="addSkill">
        <input type="text" placeholder='Just enter your skills...' v-model="skill">
        <!-- <button v-on:click="ChangeName" v-bind:disabled="btnState">{{btnName}}</button> -->
      </form>
      <ul>
        <li v-for="(value, index) in skills" :key='index'>
          {{value.skill}}
        </li>
      </ul>
      <!-- <div v-bind:style="{backgroundColor:bgColor,with: bgWith, height: bgHeight, marginTop: bgMarginTop}"> -->
          <p>These are the skills that you possess.</p>
      <!-- </div> -->
      </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      title: "My title",
      btnName: "Change",
      btnState: true,
      skill: '',
      skills: [
        {'skill': 'First skill'},
        {'skill': 'Second skill'}
      ],
      bgColor: 'lightgrey',
      bgWith: '100%',
      bgHeight: '25px',
      bgMarginTop: '25px',
      txtPlaceholder: 'Just enter your skills...',
    }
  },
  methods:{
    addSkill: function() {
      this.skills.push({skill: this.skill});
      this.skill= '';
    }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../css/skills.css"></style>
