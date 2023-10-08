<template>
  <form @submit.prevent="generate">
    <div class="input">
      <vs-input placeholder="Enter some text to generate an image" v-model="value" />
    </div>

    <div class="button">
      <vs-button flat :active="true" :disabled="value === ''"> Generate Image </vs-button>
    </div>
  </form>
</template>

<script>
export default {
  data: () => ({
    value: ''
  }),
  methods: {
    generate() {
      this.$emit('generate', this.value)
    }
  }
}
</script>

<style>
form {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  gap: 0.25rem;
}
form .input {
  width: 85%;
}
form .input input {
  width: 100%;
}

form .button {
  width: 15%;
  text-wrap: nowrap;
}
form div button.vs-button--flat.vs-button--active {
  width: 100%;
  border: 1px solid hsla(160, 100%, 37%, 1);
  background-color: hsla(160, 100%, 37%, 1);
  /* color: hsla(160, 100%, 37%, 1); */
  color: white;
  font-weight: 600;
}
</style>
