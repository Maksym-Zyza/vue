<template>
  <div class="login-wrapper">
    <div>Message: {{ message }}</div>
    <form @submit.prevent="submitForm">
      <label for="name">Name:</label>
      <input type="text" v-model="name" />
      <label for="email">Email:</label>
      <input type="text" v-model="email" />
      <button type="submit">Submit</button>
    </form>

    <ul v-if="submissions.length > 0">
      <li v-for="(item, index) in submissions" :key="index">
        {{ item.name }} {{ item.email }}
        <button @click="deleteSubmission(index)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: "",
      submissions: [],
    };
  },
  methods: {
    submitForm() {
      if (this.validation()) {
        const newSubmission = {
          name: this.name,
          email: this.email,
        };
        this.submissions.push(newSubmission);
        this.resetForm();
      }
    },
    validation() {
      if (!this.name || !this.email) {
        alert("Please fill in all fields.");
        return false;
      } else {
        return true;
      }
    },
    resetForm() {
      this.name = "";
      this.email = "";
    },
    deleteSubmission(index) {
      this.submissions.splice(index, 1);
    },
  },
  computed: {
    message() {
      const count = this.submissions.length;
      return !count ? "No submissions" : `Submissions count: ${count}`;
    },
  },
};
</script>

<style scoped>
.login-wrapper {
  margin: 5%;
  width: 100%;
  margin: 10px auto;
  padding: 10px 0;
  text-align: center;
  outline: 1px solid teal;

  div {
    margin: 20px 0;
  }

  form {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    input {
      margin: 10px 0;
    }
  }
}
</style>
