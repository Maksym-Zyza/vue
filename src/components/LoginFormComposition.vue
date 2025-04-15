<script setup>
import { ref, computed } from "vue";

const name = ref("");
const email = ref("");
const submissions = ref([]);

const message = computed(() => {
  const count = submissions.value.length;
  return count === 0 ? "No submissions" : `Submissions count: ${count}`;
});

const validation = () => {
  if (!name.value || !email.value) {
    alert("Please fill in all fields.");
    return false;
  }
  return true;
};

const submitForm = () => {
  if (validation()) {
    const newSubmission = {
      name: name.value,
      email: email.value,
    };
    submissions.value.push(newSubmission);
    resetForm();
  }
};

const resetForm = () => {
  name.value = "";
  email.value = "";
};

const deleteSubmission = (index) => {
  submissions.value = submissions.value.filter((_, i) => i !== index);
};
</script>

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
