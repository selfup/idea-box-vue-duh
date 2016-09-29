<template>
  <div>
    Title:
    <input v-model='title'>
    <br><br>
    Body:
    <input v-model='body'>
    <br><br>
    <button @click='submit'>Submit</button>
  </div>
</template>

<script>
export default {
  props: ['addIdea'],
  data() {
    return {
      title: '',
      body: ''
    }
  },
  methods: {
    generateIdea() {
      return {title: this.title, body: this.body, quality: "swill"}
    },
    submit() {
      this.addIdea(this.generateIdea())
      this.title = ''
      this.body = ''
    }
  }
}
</script>