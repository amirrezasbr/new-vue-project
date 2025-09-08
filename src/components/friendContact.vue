<template>
  <li>
    <h2>{{ name }} {{ isFavorite ? "(favorite)" : "" }}</h2>
    <button @click="toggleFavorites">toggle favorite</button>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "hide" : "Show Details" }}
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone:</strong>{{ phoneNumber }}</li>
      <li><strong>Email:</strong>{{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  emits: ["toggle-favorite"],
  props: {
    id: {
      type: String,
      default: "",
    },
    name: {
      type: String,
      default: "",
    },
    phoneNumber: {
      type: String,
      default: "",
    },
    email: {
      type: String,
      default: "",
    },
    isFavorite: {
      type: Boolean,
      default: false,
      // default: "0",
      // validator: function (value) {
      //   return value === "1" || value === "0";
      // },
    },
  },
  // props:[
  //     'name',
  //     'phoneNumber',
  //     'email',
  //     'isFavorite',
  // ],
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorites() {
      this.$emit("toggle-favorite", this.id);
      //   this.friendIsFavorite = !this.friendIsFavorite;
    },
  },
};
</script>

<style></style>
