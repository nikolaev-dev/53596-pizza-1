<template>
  <div class="content__dough">
    <div class="sheet">
      <h2 class="title title--small sheet__title">Выберите тесто</h2>

      <div class="sheet__content dough">
        <label
          v-for="item in dough"
          :key="item.value"
          :class="`dough__input dough__input--${item.value}`"
        >
          <input
            type="radio"
            name="dought"
            value="{item.value}"
            class="visually-hidden"
            checked
          />
          <b>{{ item.name }}</b>
          <span>{{ item.description }}</span>
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BuilderDoughSelector",
  data: function () {
    return {
      dough: [
        {
          name: "Тонкое",
          image: "/public/img/dough-light.svg",
          description: "Из твердых сортов пшеницы",
          price: 300,
          value: "light",
        },
        {
          name: "Толстое",
          image: "/public/img/dough-large.svg",
          description: "Из твердых сортов пшеницы",
          price: 300,
          value: "large",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
