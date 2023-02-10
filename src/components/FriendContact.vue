<template>
  <li class="list-none mt-4">
    <h2 class="text-xl">{{ name }} {{ isFavorite ? "(Favorite)" : "" }}</h2>
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
    <button
      @click="$emit('delete', id)"
      class="border border-indigo-500 bg-indigo-500 text-white rounded-md px-3 py-1 transition duration-500 ease select-none hover:bg-indigo-600 focus:outline-none focus:shadow-outline"
    >
      Delete
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong>{{ phone }}</li>
      <li><strong>Email: </strong>{{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
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
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.id);
    },
  },
};
</script>
