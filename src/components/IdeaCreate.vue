<template>
  <div>
    <form @submit.prevent="create">
      <label for="idea-title">Ideas Title</label>
      <br />
      <input id="idea-title" type="text" v-model="title" />
      <br />
      <button type="submit">Create</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: ""
    };
  },
  methods: {
    create() {
      const idea = {
        createAt: new Date(),
        title: this.title
      };
      //this.$store.commit('CREATE_IDEAS', idea)
      this.$store.dispatch("createIdea", idea);
      this.title = "";
    }
  }
};
</script>

<style lang="scss" scoped></style>
