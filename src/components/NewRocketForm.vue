<template>
<section>
  <button 
  @click="showForm = !showForm"
  type="button" 
  class="btn btn-danger">
  Show Form
  </button>
  <form v-if="showForm" @submit.prevent="onAddRocket">
    <div class="form-group">
      <label for="name">Name</label>
      <input v-model="rocket.name" type="text" name="name" class="form-control" id="name" value="">
    </div>
    <div class="form-group">
      <label for="country">Country</label>
      <input v-model="rocket.country" type="text" name="country" class="form-control" id="country" value="">
    </div>
    <div class="form-group">
      <label for="description">Description</label>
      <textarea v-model="rocket.description" type="text" name="description" class="form-control" id="description" value=""></textarea>
    </div>
    <div class="form-group">
      <label for="image">Image</label>
      <input v-model="rocket.image" type="text" name="image" class="form-control" id="image" value="">
    </div>
    <button type="submit" class="btn btn-success">Add Rocket</button>
  </form>
  </section>
</template>

<script>
function getEmptyRocket() {
  return {
      name: '',
      description: '',
      country: '',
      image: '',
    };
}

export default {
  props: ['addRocket'],
  data: () => ({
    showForm: false,
    rocket: getEmptyRocket(),
  }),
  methods: {
    onAddRocket() {
      this.addRocket(this.rocket);
      this.rocket = getEmptyRocket();
      this.showForm = false;
    },
  },
};
</script>

<style lang="css">

</style>
