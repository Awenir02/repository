<template>
  <header class="header">
    <div>
      <!-- Изображение, при нажатии на которое будет появляться меню -->
      <img class="Menu" src="/images/menu-Regular.png" alt="Click me" @click.stop="toggleMenu" />

      <!-- Выпадающее меню -->
      <div v-if="isMenuVisible" class="dropdown-menu" ref="dropdownMenu">
        <!-- Изображение для закрытия меню -->
        <img src="/images/close.png" alt="Close" class="close-icon" @click="closeMenu" />
        <ul>
          <li><a href="#">Solid parfume</a></li>
          <li><a href="#">Scented Ovals</a></li>
          <li><a href="#">Scented Candles</a></li>
          <li><a href="#">Wishlist</a></li>
          <li><a href="#">Contacts</a></li>
        </ul>
      </div>
    </div>
    <div class="left-section">
      <span class="phrase">Solid parfume</span>
      <span class="phrase">Scented Ovals</span>
      <span class="phrase">Scented Candles</span>
    </div>
    <div class="center-section">
      <img src="/images/Vector.png" alt="Center Icon" class="center-icon" />
    </div>
    <div class="right-section">
      <img src="/images/user_icn.png" alt="Icon 1" class="icon" />
      <img src="/images/Heart.png" alt="Icon 2" class="icon" />
      <img src="/images/cart_icn (1).png" alt="Icon 3" class="icon" />
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      isMenuVisible: false, // Состояние видимости меню
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible; // Переключаем видимость меню
    },
    closeMenu() {
      this.isMenuVisible = false; // Закрываем меню
    },
    handleClickOutside(event) {
      // Проверяем, был ли клик вне меню
      if (
        this.isMenuVisible &&
        this.$refs.dropdownMenu &&
        !this.$refs.dropdownMenu.contains(event.target)
      ) {
        this.closeMenu(); // Закрываем меню
      }
    },
  },
  mounted() {
    // Добавляем обработчик клика на весь документ
    document.addEventListener("click", this.handleClickOutside);
  },
  beforeUnmount() {
    // Убираем обработчик при уничтожении компонента
    document.removeEventListener("click", this.handleClickOutside);
  },
};
</script>

<style>
@font-face {
  font-family: Mukta; /* Гарнитура шрифта */
  src: url(/fonts/MuktaVaani-Light.ttf); /* Путь к файлу со шрифтом */
}
@font-face {
  font-family: Marcellus; /* Гарнитура шрифта */
  src: url(/fonts/MarcellusSC-Regular.ttf); /* Путь к файлу со шрифтом */
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 5%;
  background-color: #f8f8f8;
  border-bottom: 1px solid #ddd;
}

.left-section {
  display: flex;
  gap: 15px;
  padding-left: 10%;
  margin: 0 auto;
}

.phrase {
  font-size: 17px;
  color: black;
  font-family: Mukta;
}

.center-section {
  flex-grow: 1;
  text-align: center;
}

.center-icon {
  width: 40px;
  height: 40px;
}

.right-section {
  display: flex;
  gap: 15px;
  padding-right: 10%;
  margin: 0 auto;
}

.icon {
  width: 24px;
  height: 24px;
}
.dropdown-menu {
  position: absolute;
  background-color: #f9f9f9;
  top: 0;
  left: 0;
  min-width: 160px;
  z-index: 1;
  padding: 40px; /* Отступ сверху для иконки закрытия */
  border: 1px solid #59260b;
}

.close-icon {
  position: absolute;
  top: 10px;
  left: 10px;
  cursor: pointer;
  width: 20px; /* Размер иконки */
  height: 20px;
}

.dropdown-menu ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.dropdown-menu ul li a {
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  color: black;
  font-size: 32px;
}

.dropdown-menu ul li a:hover {
  background-color: #f1f1f1;
}
.Menu {
  left: 0;
  display: none;
}
@media (max-width: 768px) {
  .header {
    padding: 0 2%;
  }
  .right-section {
    padding-right: 2%;
  }
  .left-section {
    display: none;
  }
  .Menu {
    display: block;
  }
}
@media (max-width: 360px) {
  .icon1 {
    display: none;
  }
}
</style>
