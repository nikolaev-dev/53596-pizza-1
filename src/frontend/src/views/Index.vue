<template>
  <main class="content">
    <form action="#" method="post">
      <div class="content__wrapper">
        <h1 class="title title--big">Конструктор пиццы</h1>

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
                  :value="item.value"
                  class="visually-hidden"
                  checked
                />
                <b>{{ item.name }}</b>
                <span>{{ item.description }}</span>
              </label>
            </div>
          </div>
        </div>

        <div class="content__diameter">
          <div class="sheet">
            <h2 class="title title--small sheet__title">Выберите размер</h2>

            <div class="sheet__content diameter">
              <label
                v-for="item in sizes"
                :key="item.value"
                :class="`diameter__input diameter__input--${item.value}`"
              >
                <input
                  type="radio"
                  name="diameter"
                  :value="item.value"
                  class="visually-hidden"
                />
                <span>{{ item.name }}</span>
              </label>
            </div>
          </div>
        </div>

        <div class="content__ingridients">
          <div class="sheet">
            <h2 class="title title--small sheet__title">
              Выберите ингридиенты
            </h2>

            <div class="sheet__content ingridients">
              <div class="ingridients__sauce">
                <p>Основной соус:</p>

                <label
                  v-for="item in sauces"
                  :key="item.value"
                  class="radio ingridients__input"
                >
                  <input
                    type="radio"
                    name="sauce"
                    :value="item.value"
                    checked
                  />
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
                    <span :class="`filling filling--${item.value}`">
                      {{ item.name }}
                    </span>

                    <div class="counter counter--orange ingridients__counter">
                      <button
                        type="button"
                        class="
                          counter__button
                          counter__button--disabled
                          counter__button--minus
                        "
                      >
                        <span class="visually-hidden">Меньше</span>
                      </button>
                      <input
                        type="text"
                        name="counter"
                        class="counter__input"
                        value="0"
                      />
                      <button
                        type="button"
                        class="counter__button counter__button--plus"
                      >
                        <span class="visually-hidden">Больше</span>
                      </button>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>

        <div class="content__pizza">
          <label class="input">
            <span class="visually-hidden">Название пиццы</span>
            <input
              type="text"
              name="pizza_name"
              placeholder="Введите название пиццы"
            />
          </label>

          <div class="content__constructor">
            <div class="pizza pizza--foundation--big-tomato">
              <div class="pizza__wrapper">
                <div class="pizza__filling pizza__filling--ananas"></div>
                <div class="pizza__filling pizza__filling--bacon"></div>
                <div class="pizza__filling pizza__filling--cheddar"></div>
              </div>
            </div>
          </div>

          <div class="content__result">
            <p>Итого: 0 ₽</p>
            <button type="button" class="button button--disabled" disabled>
              Готовьте!
            </button>
          </div>
        </div>
      </div>
    </form>
  </main>
</template>

<script>
export default {
  name: "App",
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
