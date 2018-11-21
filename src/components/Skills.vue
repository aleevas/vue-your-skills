<template>
  <div class="container">
    <div class="holder">
      <h1>{{title}}</h1>
      <form @submit.prevent="addSkill">
        <input type="text" placeholder='Just enter your skills...' v-model="skill" name="skill" v-validate="'min:3'" />
        <!-- <button v-on:click="ChangeName" v-bind:disabled="btnState">{{btnName}}</button> -->
         <!-- <input type="checkbox" id="checkbox" v-model="checked"> -->
      <transition name="alert-in" enter-active-class="animated flipInX" leave-active-class="animated flipOutX">
        <p class="alert" v-if="errors.has('skill')">{{ errors.first('skill') }}</p>
      </transition>
      </form>
      <ul>
          <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
          <li v-for="(value, index) in skills" :key='index'>
            {{value.skill}}
            <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
          </li>
          </transition-group>
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
      checked: false, 
    }
  },
  methods:{
    addSkill: function() {
      this.$validator.validateAll().then((result => {
        if (result) {
          this.skills.push({skill: this.skill});
          this.skill= '';
        }
        else {
          alert('It\'s wrong skill! Please try a new one!');
        }
      }));

    },
    remove: function(id) {
      this.skills.splice(id, 1);
    }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="../css/skills.css"></style>
