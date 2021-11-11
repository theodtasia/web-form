<template>
  <form
    @submit.prevent="handleSubmit"
    class="max-w-10 p-4 text-left bg-gray-100"
  >
    <label>Email</label>
    <input
      type="ema
il"
      required
      v-model="email"
    />
    <label>Password</label>
    <input type="password" required v-model="password" />
    <div v-if="error" class="error">{{ error }}</div>
    <label>Student:</label>
    <select v-model="student">
      <option value="undergraduated">UnderGraduated</option>
      <option value="graduated">Graduated</option>
      <option value="postgraduated">Postgraduated</option>
    </select>
    <div class="terms bg-gray-50">
      <input type="checkbox" v-model="terms" required />
      <label>Accept terms and conditions</label>
    </div>
    <div class="submit">
      <button class=" rounded-full p-4 font-extrabold bg-green-200">
        Submit form
      </button>
    </div>
  </form>

  <div class="bg-green-200">
    <p>Email: {{ email }}</p>
    <p>Password: {{ password }}</p>
    <p>Student: {{ student }}</p>
    <p>Terms: {{ terms }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      student: "",
      terms: false,
      error: "",
    };
  },
  methods: {
    handleSubmit() {
      this.error =
        this.password.length > 8 ? "" : "Password must me at least 8 chars";
    },
  },
};
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-weight: bold;
}
input,
select {
  padding: 40px 40px;
  width: 100%;
  color: rgb(252, 252, 252);
}
input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}

.submit {
  text-align: center;
}
.error {
  color: #661212;
  margin-top: 10px;
  font-size: bold;
  font-weight: bold;
}
</style>
