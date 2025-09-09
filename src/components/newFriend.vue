<template>
  <div class="form-container">
    <h3>add your friends here</h3>
    <form @submit.prevent="addFriend">
      <div>
        <label> name</label>
        <input type="text" v-model="name" placeholder="name" />
      </div>
      <div>
        <label> phone number</label>
        <input type="text" v-model="phoneNUmber" placeholder="phone number" />
      </div>
      <div>
        <label> email</label>
        <input type="text" v-model="email" placeholder="email" />
      </div>
      <button>add</button>
    </form>
  </div>
</template>

<script>
export default {
  emits: ["friend-data"],
  data() {
    return {
      name: "",
      phoneNUmber: "",
      email: "",
    };
  },
  methods: {
    addFriend() {
      this.$emit("friend-data", this.name, this.email, this.phoneNUmber);
    },
  },
};
</script>

<style>
.form-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
