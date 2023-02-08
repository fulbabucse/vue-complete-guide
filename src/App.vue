<template>
  <div class="mt-10 max-w-screen-xl mx-auto">
    <friend-contact
      name="Fahim Islam"
      phone="45545878"
      email="fahim@islam.com"
      isFavorite="0"
    ></friend-contact>
    <friend-contact
      name="Fulbabu"
      phone="454571121"
      email="ful@babu.com"
      isFavorite="1"
    ></friend-contact>
  </div>
</template>

<script>
const app = {
  data() {
    return {
      friends: [
        {
          id: "01",
          name: "Fahim Islam",
          phone: "124545",
          email: "fahim@islam.com",
        },
        {
          id: "02",
          name: "Fulbabu",
          phone: "5454545",
          email: "ful@babu.com",
        },
      ],
    };
  },
};
</script>
