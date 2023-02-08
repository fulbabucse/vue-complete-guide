<template>
  <li class="list-none mt-4">
    <h2>{{ name }}</h2>
    <button
      @click="toggleDetails"
      class="border border-indigo-500 bg-indigo-500 text-white rounded-md px-3 py-1 transition duration-500 ease select-none hover:bg-indigo-600 focus:outline-none focus:shadow-outline"
    >
      Show Details
    </button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong>{{ phone }}</li>
      <li><strong>Email: </strong>{{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: ["name", "phone", "email"],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "01",
        name: "Fahim Islam",
        phone: "124545",
        email: "fahim@islam.com",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>
