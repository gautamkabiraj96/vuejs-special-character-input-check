<template>
  <div id="app">
    <input
      type="text"
      placeholder="Type something..."
      v-model="inputValue"
      @keyup="inputContainsSpecialCharacters"
    />
    <p>
      Contains special character:
      <span v-if="inputContainsSpecialCharacter">✅ True</span>
      <span v-else>❌ False</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inputValue: null,
      inputContainsSpecialCharacter: false,
    };
  },
  methods: {
    inputContainsSpecialCharacters() {
      const specialCharacters = /[`!@#$%^&*()_+\-=\\|,.<>?~]/;
      this.inputContainsSpecialCharacter = specialCharacters.test(
        this.inputValue
      );
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
}
input {
  font-size: 16px;
  padding: 4px;
  border: 1px solid rgb(34, 34, 34);
  outline: none;
}
</style>
