<template>
  <main class="content">
    <form action="#" method="post">
      <div class="content__wrapper">
        <h1 class="title title--big">Конструктор пиццы</h1>

        <BuilderDoughSelector />
        <BuilderSizeSelector />
        <BuilderIngredientsSelector />
        <BuilderPizzaView />
      </div>
    </form>
  </main>
</template>

<script>
import BuilderDoughSelector from "./BuilderDoughSelector";
import BuilderIngredientsSelector from "./BuilderIngredientsSelector";
import BuilderPizzaView from "./BuilderPizzaView";
import BuilderSizeSelector from "./BuilderSizeSelector";

export default {
  name: "Builder",
  components: {
    BuilderDoughSelector,
    BuilderIngredientsSelector,
    BuilderPizzaView,
    BuilderSizeSelector,
  },
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
      ingredients: [
        {
          name: "Грибы",
          image: "/public/img/filling/mushrooms.svg",
          price: 33,
          value: "mushrooms",
        },
        {
          name: "Чеддер",
          image: "/public/img/filling/cheddar.svg",
          price: 42,
          value: "cheddar",
        },
        {
          name: "Салями",
          image: "/public/img/filling/salami.svg",
          price: 42,
          value: "salami",
        },
        {
          name: "Ветчина",
          image: "/public/img/filling/ham.svg",
          price: 42,
          value: "ham",
        },
        {
          name: "Ананас",
          image: "/public/img/filling/ananas.svg",
          price: 25,
          value: "ananas",
        },
        {
          name: "Бекон",
          image: "/public/img/filling/bacon.svg",
          price: 42,
          value: "bacon",
        },
        {
          name: "Лук",
          image: "/public/img/filling/onion.svg",
          price: 21,
          value: "onion",
        },
        {
          name: "Чили",
          image: "/public/img/filling/chile.svg",
          price: 21,
          value: "chile",
        },
        {
          name: "Халапеньо",
          image: "/public/img/filling/jalapeno.svg",
          price: 25,
          value: "jalapeno",
        },
        {
          name: "Маслины",
          image: "/public/img/filling/olives.svg",
          price: 25,
          value: "olives",
        },
        {
          name: "Томаты",
          image: "/public/img/filling/tomatoes.svg",
          price: 35,
          value: "tomatoes",
        },
        {
          name: "Лосось",
          image: "/public/img/filling/salmon.svg",
          price: 50,
          value: "salmon",
        },
        {
          name: "Моцарелла",
          image: "/public/img/filling/mozzarella.svg",
          price: 35,
          value: "mozzarella",
        },
        {
          name: "Пармезан",
          image: "/public/img/filling/parmesan.svg",
          price: 35,
          value: "parmesan",
        },
        {
          name: "Блю чиз",
          image: "/public/img/filling/blue_cheese.svg",
          price: 50,
          value: "blue_cheese",
        },
      ],
      sauces: [
        {
          name: "Томатный",
          price: 50,
        },
        {
          name: "Сливочный",
          price: 50,
        },
      ],
      sizes: [
        {
          name: "23 см",
          image: "/public/img/diameter.svg",
          multiplier: 1,
          value: "small",
        },
        {
          name: "32 см",
          image: "/public/img/diameter.svg",
          multiplier: 2,
          value: "normal",
        },
        {
          name: "45 см",
          image: "/public/img/diameter.svg",
          multiplier: 3,
          value: "big",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
