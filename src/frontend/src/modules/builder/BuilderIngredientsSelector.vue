<template>
  <div class="content__ingridients">
    <div class="sheet">
      <h2 class="title title--small sheet__title">Выберите ингридиенты</h2>

      <div class="sheet__content ingridients">
        <div class="ingridients__sauce">
          <p>Основной соус:</p>

          <label
            v-for="item in sauces"
            :key="item.value"
            class="radio ingridients__input"
          >
            <input type="radio" name="sauce" value="tomato" checked />
            <span> {{ item.name }}</span>
          </label>
        </div>

        <div class="ingridients__filling">
          <p>Начинка:</p>

          <ul class="ingridients__list">
            <li
              v-for="item in ingredients"
              :key="item.name"
              class="ingridients__item"
            >
              <span :class="`filling filling--${item.value}`">{{
                item.name
              }}</span>

              <ItemCounter />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ItemCounter from "../../common/components/ItemCounter";
export default {
  name: "BuilderIngredientsSelector",
  components: { ItemCounter },
  data: function () {
    return {
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
    };
  },
};
</script>

<style scoped></style>
