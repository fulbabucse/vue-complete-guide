<template>
  <li class="list-none mt-4">
    <h2 class="text-xl">
      {{ name }} {{ friendIsFavorite === "1" ? "(Favorite)" : "" }}
    </h2>
    <button
      @click="toggleDetails"
      class="border border-indigo-500 bg-indigo-500 text-white rounded-md px-3 py-1 transition duration-500 ease select-none hover:bg-indigo-600 focus:outline-none focus:shadow-outline"
    >
      Show Details
    </button>
    <button
      @click="toggleFavorite"
      class="border border-indigo-500 bg-indigo-500 text-white rounded-md px-3 py-1 transition duration-500 ease select-none hover:bg-indigo-600 focus:outline-none focus:shadow-outline"
    >
      Toggle Favorite
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong>{{ phone }}</li>
      <li><strong>Email: </strong>{{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  // props: ["name", "phone", "email", "isFavorite"],
  props: {
    name: {
      type: String,
      required: true,
    },
    phone: {
      type: String,
      required: true,
    },
    email: {
      type: String,
      required: true,
    },
    isFavorite: {
      type: String,
      required: false,
      default: "0",
      validator: (value) => {
        return value === "0" || "1";
      },
    },
  },
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "01",
        name: "Fahim Islam",
        phone: "124545",
        email: "fahim@islam.com",
      },
      friendIsFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      if (this.friendIsFavorite === "1") {
        this.friendIsFavorite = "0";
      } else {
        this.friendIsFavorite = "1";
      }
    },
  },
};
</script>
