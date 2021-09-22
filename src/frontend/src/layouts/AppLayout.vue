<template>
  <header class="header">
    <div class="header__logo">
      <a href="index.html" class="logo">
        <img
          src="img/logo.svg"
          alt="V!U!E! Pizza logo"
          width="90"
          height="40"
        />
      </a>
    </div>
    <div class="header__cart">
      <a href="cart.html">0 ₽</a>
    </div>
    <div class="header__user">
      <a href="user-data.html">
        <picture>
          <source
            type="image/webp"
            srcset="img/users/user5.webp 1x, img/users/user5@2x.webp 2x"
          />
          <img
            src="img/users/user5.jpg"
            srcset="img/users/user5@2x.jpg"
            alt="Василий Ложкин"
            width="32"
            height="32"
          />
        </picture>
        <span>Василий Ложкин</span>
      </a>
      <a href="#" class="header__logout"><span>Выйти</span></a>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppLayout",
};
</script>
