<script setup>
import Header from "./Header.vue";
</script>

<template>
  <div class="Head">
    <Header />
    <div class="header-down">
      <div class="container">
        <div class="header-title">
          SOLID PARFUME AND<br />
          CENTED CANDLES FOR<br />
          COZY HOME<br />
        </div>
        <button class="header-button">Shop now</button>
      </div>
      <div class="img-container" style="width: 100%">
        <div style="width: 100%; max-width: 768px; height: 400px; overflow: hidden">
          <img
            class="woman"
            src="\images\Woman.png"
            alt="solidparfume"
            style="object-fit: cover; width: 100%; height: 100%; object-position: top"
          />
        </div>
      </div>
    </div>
    <img src="\images\Woman.png" alt="Large Image" class="large-image" />
    <img src="\images\svecha.png" alt="Small Image" class="small-image" />

    <div class="txtcontainer">
      <div class="txt1">All Natural Ingredients</div>
      <div class="txt2">
        Believing that quality will foster radiance and inspire overall sense of well being
      </div>
    </div>
  </div>
  <div class="catalogue">
    <div class="catalogue-container">
      <div class="catalogue-title">Shop by categories</div>
      <div class="catalogue-images">
        <div class="image-wrapper" style="left: 0%">
          <div class="image-overlay">
            <div class="overlay-text">Solid Parfume</div>
          </div>
          <div style="width: 594px; height: 400px; overflow: hidden">
            <img
              class="images1"
              src="\images\solidparfume.jpg"
              alt="solidparfume"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <div class="image-wrapper" style="left: 0%; top: 430px">
          <div class="image-overlay">
            <div class="overlay-text">Solid Parfume</div>
          </div>
          <div style="width: 594px; height: 400px; overflow: hidden">
            <img
              class="images2"
              src="\images\scantedovals.jpg"
              alt="scantedovals"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <div class="image-wrapper" style="left: 50%">
          <div class="image-overlay1">
            <div class="overlay-text">Solid Parfume</div>
          </div>
          <div style="width: 594px; height: 830px; overflow: hidden">
            <img
              class="images3"
              src="\images\scantedcandles.jpg"
              alt="scantedcandles"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="list">
    <div class="list-container">
      <div class="popular-flavors">POPULAR FLAVORS</div>
      <div class="scroll-container">
        <button class="scroll-button left" @click="scrollLeft">&#10094;</button>
        <div class="card-line" ref="cardLine">
          <div class="card-container" v-for="(card, index) in cards1" :key="index">
            <div class="card-image" @click="toggleHeart(index)">
              <img
                :src="card.isLiked ? '/images/heart_filled.png' : '/images/heart_icn.png'"
                alt="heart"
                :class="{ 'heart-animation': card.isLiked }"
              />
              <img
                src="/images/lock.png"
                alt="lock"
                class="lock-icon"
                style="width: 14px; height: 16px"
              />
            </div>
            <img :src="card.image" :alt="card.alt" class="card-main-image" />
            <button class="add-to-bag">Add to Bag</button>
            <div class="card-text">
              {{ card.title }}<br />
              {{ card.subtitle }}<br />
              {{ card.price }}<br />
            </div>
          </div>
        </div>
        <button class="scroll-button right" @click="scrollRight">&#10095;</button>
      </div>
      <!-- Индикаторы -->
      <div class="indicators">
        <div
          v-for="(indicator, index) in indicators"
          :key="index"
          class="indicator"
          :class="{ active: currentGroup === index }"
          @click="scrollToGroup(index)"
        ></div>
      </div>
    </div>
  </div>
  <div class="catalogue">
    <div class="blog-container">
      <div class="catalogue-title">Read our Blog</div>
      <div class="catalogue-images">
        <div class="image-wrapper1" style="left: 0%">
          <div class="blog-overlay">
            <div class="blog-text">Our Charity Mission</div>
          </div>
          <div style="width: 490px; height: 700px; overflow: hidden">
            <img
              class="imagesblog1"
              src="\images\blog1.jpg"
              alt="solidparfume"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <div class="image-wrapper1" style="left: 42%; top: 0px">
          <div class="blog-overlay">
            <div class="blog-text">Why Solid?</div>
          </div>
          <div style="width: 282px; height: 400px; overflow: hidden">
            <img
              class="imagesblog2"
              src="\images\blog2.jpg"
              alt="scantedovals"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <div class="image-wrapper1" style="left: 67%">
          <div class="blog-overlay">
            <div class="blog-text">POV</div>
          </div>
          <div style="width: 382px; height: 316px; overflow: hidden">
            <img
              class="imagesblog3"
              src="\images\blog3.jpg"
              alt="scantedcandles"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <div class="image-wrapper1" style="left: 42%; top: 430px">
          <div class="blog-overlay">
            <div class="blog-text">Our Sustainable Practice</div>
          </div>
          <div style="width: 698px; height: 270px; overflow: hidden">
            <img
              class="imagesblog4"
              src="\images\blog4.jpg"
              alt="scantedovals"
              style="object-fit: cover; width: 100%; height: 100%"
            />
          </div>
        </div>
        <button class="blog-button">Read more in our Blog</button>
      </div>
    </div>
  </div>
  <div class="list">
    <div class="list-container">
      <div class="popular-flavors">You may also like</div>
      <div class="scroll-container">
        <button class="scroll-button left" @click="scrollLeft">&#10094;</button>
        <div class="card-line" ref="cardLine">
          <div class="card-container" v-for="(card, index) in cards2" :key="index">
            <div class="card-image" @click="toggleHeart(index)">
              <img
                :src="card.isLiked ? '/images/heart_filled.png' : '/images/heart_icn.png'"
                alt="heart"
                :class="{ 'heart-animation': card.isLiked }"
              />
              <img
                src="/images/lock.png"
                alt="lock"
                class="lock-icon"
                style="width: 14px; height: 16px"
              />
            </div>
            <img :src="card.image" :alt="card.alt" class="card-main-image" />
            <button class="add-to-bag">Add to Bag</button>
            <div class="card-text">
              {{ card.title }}<br />
              {{ card.subtitle }}<br />
              {{ card.price }}<br />
            </div>
          </div>
        </div>
        <button class="scroll-button right" @click="scrollRight">&#10095;</button>
      </div>
      <!-- Индикаторы -->
      <div class="indicators">
        <div
          v-for="(indicator, index) in indicators"
          :key="index"
          class="indicator"
          :class="{ active: currentGroup === index }"
          @click="scrollToGroup(index)"
        ></div>
      </div>
    </div>
  </div>
  <div class="touch">
    <div>
      <img src="\images\photo.png" alt="" class="photo" />
    </div>
    <div class="get-in-touch">
      <div class="get-in-touch-text-height">GET IN TOUCH</div>
      <div class="get-in-touch-text">
        Get daily expert perfume tips, special temporal promotions and an extra discount for
        internet payments.
      </div>
      <div class="email-input">
        <input type="email" placeholder="Enter your email" />
      </div>
      <div class="get-in-touch-text">
        By clicking OK, I agree to the <a href="#">Terms and Conditions</a> and the
        <a href="#">Privacy Policy</a>
      </div>
      <button class="Submit">Submit</button>
    </div>
  </div>
  <div class="footer">
    <div class="footer-container">
      <div class="vector">
        <img class="vectorimg" src="\images\VectorWhite.png" alt="vector" />
      </div>
      <div class="footer-nav">
        <ul>
          <li><a href="" style="font-weight: bold">Products</a></li>
          <li><a href="">Solid parfume</a></li>
          <li><a href="">Scented Ovsls</a></li>
          <li><a href="">Scented Candles</a></li>
          <li><a href="" style="font-weight: bold">About us</a></li>
          <li><a href="">Our story</a></li>
          <li><a href="">Blog</a></li>
          <li><a href="">Contacts</a></li>
          <li><a href="" style="font-weight: bold">Social</a></li>
          <li><a href="">Instagram</a></li>
          <li><a href="">Twitter</a></li>
          <li><a href="">Facebook</a></li>
          <li><a href="">60 Midway Road, Suite 12</a></li>
          <li><a href="">Green Bay WI 54328</a></li>
          <li><a href="">407-280-4690</a></li>
        </ul>
      </div>
      <div class="footer-bottom">
        <p>&copy;2022 SV Shop. All rights reserved.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards1: [
        {
          image: "/images/card1.png",
          alt: "card1",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card2.png",
          alt: "card2",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card3.png",
          alt: "card3",
          title: "Bergamot",
          subtitle: "Scented Candle",
          price: "$69.00",
        },
        {
          image: "/images/card4.png",
          alt: "card4",
          title: "Odour Removing Candle with Basil",
          subtitle: "Scented Candle",
          price: "$82.00",
        },
        {
          image: "/images/card1.png",
          alt: "card1",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card2.png",
          alt: "card2",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card3.png",
          alt: "card3",
          title: "Bergamot",
          subtitle: "Scented Candle",
          price: "$69.00",
        },
        {
          image: "/images/card4.png",
          alt: "card4",
          title: "Odour Removing Candle with Basil",
          subtitle: "Scented Candle",
          price: "$82.00",
        },
        {
          image: "/images/card1.png",
          alt: "card1",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card2.png",
          alt: "card2",
          title: "Boulevard Saint Germain",
          subtitle: "Scented Oral",
          price: "$35.00",
        },
        {
          image: "/images/card3.png",
          alt: "card3",
          title: "Bergamot",
          subtitle: "Scented Candle",
          price: "$69.00",
        },
        {
          image: "/images/card4.png",
          alt: "card4",
          title: "Odour Removing Candle with Basil",
          subtitle: "Scented Candle",
          price: "$82.00",
        },
      ],
      currentIndex: 0,
      indicators: [0, 1, 2],
      currentGroup: 0,

      cards2: [
        {
          image: "/images/like1.png",
          alt: "card1",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like2.png",
          alt: "card2",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like3.png",
          alt: "card3",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like4.png",
          alt: "card4",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$196.00",
        },
        {
          image: "/images/like1.png",
          alt: "card1",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like2.png",
          alt: "card2",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like3.png",
          alt: "card3",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like4.png",
          alt: "card4",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$196.00",
        },
        {
          image: "/images/like1.png",
          alt: "card1",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like2.png",
          alt: "card2",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like3.png",
          alt: "card3",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$105.00",
        },
        {
          image: "/images/like4.png",
          alt: "card4",
          title: "Rose Frankincense & Patchouli",
          subtitle: "Scented Candle",
          price: "$196.00",
        },
      ],
      currentIndex: 0,
      indicators: [0, 1, 2],
      currentGroup: 0,
    };
  },
  computed: {
    visibleCards() {
      return this.cards1.slice(this.currentIndex, this.currentIndex + 4);
    },
  },
  methods: {
    toggleHeart(index) {
      this.cards1[index].isLiked = !this.cards1[index].isLiked;
    },
    scrollLeft() {
      if (this.currentIndex > 0) {
        this.currentIndex -= 4;
      } else {
        this.currentIndex = this.cards1.length - 4;
      }
      this.updateCurrentGroup();
      this.scrollToCurrentIndex();
    },
    scrollRight() {
      if (this.currentIndex + 4 < this.cards1.length) {
        this.currentIndex += 4;
      } else {
        this.currentIndex = 0;
      }
      this.updateCurrentGroup();
      this.scrollToCurrentIndex();
    },
    scrollToCurrentIndex() {
      const cardLine = this.$refs.cardLine;
      const cardWidth = cardLine.querySelector(".card-container").offsetWidth;
      const gap = 50;
      cardLine.scrollTo({
        left: this.currentIndex * (cardWidth + gap),
        behavior: "smooth",
      });
    },
    updateCurrentGroup() {
      this.currentGroup = Math.floor(this.currentIndex / 4);
    },
    scrollToGroup(groupIndex) {
      this.currentIndex = groupIndex * 4;
      this.currentGroup = groupIndex;
      this.scrollToCurrentIndex();
    },
  },
  mounted() {
    window.addEventListener("resize", this.updateCurrentGroup);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.updateCurrentGroup);
  },
};
</script>
<style>
@font-face {
  font-family: Mukta;
  src: url(/fonts/MuktaVaani-Light.ttf);
}
@font-face {
  font-family: Marcellus;
  src: url(/fonts/MarcellusSC-Regular.ttf);
}
.header-down {
  background-color: #edebe8;
  height: 863px;
  position: relative;
}
.container {
  left: 351px;
  top: 180px;
  height: 374px;
  flex-direction: column;
  display: flex;
  /justify-content: space-between;
  padding-top: 5%;
}
.header-title {
  padding-left: 5%;
  margin: 0 0;
  font-size: 62px;
  font-weight: 400;
  column-count: 1;
  gap: 10px;
  color: #59260b;
  font-family: Marcellus;
  max-width: 700px;
}

.header-button {
  background-color: #59260b;
  padding: 14px 28px;
  color: #ffffff;
  font-size: 17px;
  font-weight: 300;
  font-family: Pompadur;
  text-decoration: none;
  position: relative;
  margin: 5% 12% 5%;
  width: 170px;
}

.large-image {
  position: absolute;
  top: 110px;
  left: 55%;
  width: 40%;
  height: auto;
}

.small-image {
  position: absolute;
  top: 474px;
  left: 50%;
  width: 22%;
  height: auto;
}
.txtcontainer {
  position: relative;
  margin: 10% 20%;
  border-right: 2px solid #c5b0aa;
  border-left: 2px solid #c5b0aa;
}
.txt1 {
  text-align: center;
  font-size: 72px;
  color: #59260b;
  font-family: Marcellus;
}
.txt2 {
  text-align: center;
  font-size: 36px;
  color: #59260b;
  font-family: Mukta;
}
.catalogue {
  width: 100%;
  margin: auto;
}
.catalogue-container {
  margin: auto;
  position: relative;
  max-width: 1218px;
  height: 1100px;
}
.catalogue-title {
  text-align: center;
  margin: auto;
  width: 405px;
  height: 60px;
  font-size: 48px;
  font-weight: 400;
  font-family: Marcellus;
  padding-bottom: 20px;
}
.catalogue-images {
  position: relative;
  width: 100%;
  margin: 0 auto;
  max-width: 1218px;
}
.image-wrapper {
  position: absolute;
  border: 2px solid #c5b0aa;
  width: 60%;
  max-width: 594px;
  height: 400px;
  overflow: hidden;
}
.image-wrapper:nth-child(1) {
  left: 0;
  top: 0;
  height: 400px;
}

.image-wrapper:nth-child(2) {
  left: 0;
  top: 430px;
  height: 400px;
}

.image-wrapper:nth-child(3) {
  left: 50%;
  top: 0;
  height: 830px;
}
.images1,
.images2,
.images3 {
  display: block;
  width: 100%;
  height: 400px;
}
.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 70px;
  background-color: #edebe8;
  color: #000000;
  text-align: center;
  z-index: 1;
  text-align: center;
  margin: 0 auto;
}
.image-overlay1 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 70px;
  background-color: #59260b;
  color: white;
  text-align: center;
  z-index: 1;
  text-align: center;
  margin: 0 auto;
}
.overlay-text {
  font-size: 17px;
  font-weight: 300px;
  top: 30%;
  position: relative;
  font-family: Mukta;
  font-weight: bold;
}

.photo {
  width: 100%;
  height: 100%;
}
.img-container {
  display: none;
}
@media (max-width: 768px) {
  .scroll-button {
    display: none;
  }

  .card-line {
    overflow-x: scroll;
  }
  .photo {
    width: 100%;
    height: 100%;
  }
  .img-container {
    display: block;
    position: relative;
  }
  .container {
    height: 200px;
  }
}
.blog {
  width: 100%;
  margin: auto;
}
.blog-container {
  margin: auto;
  position: relative;
  max-width: 1218px;
  height: 1100px;
}
.blog-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 70px;
  background-color: #edebe8;
  color: #000000;
  text-align: center;
  z-index: 1;
  /text-align: center;
  margin: 0 auto;
}
.blog-text {
  font-size: 17px;
  font-weight: 300px;
  top: 40%;
  position: relative;
  font-family: Mukta;
  font-weight: bold;
}
.image-wrapper1 {
  position: absolute;
  border: 2px solid #c5b0aa;
  height: 400px;
  overflow: hidden;
}
.image-wrapper1:nth-child(1) {
  left: 0;
  top: 0;
  height: 700px;
}

.image-wrapper1:nth-child(2) {
  left: 0;
  top: 430px;
  height: 400px;
}

.image-wrapper1:nth-child(3) {
  left: 50%;
  top: 0;
  height: 320px;
  max-width: 386px;
}
.image-wrapper1:nth-child(4) {
  left: 50%;
  top: 0;
  height: 270px;
}

.imagesblog1,
.imagesblog2,
.imagesblog3,
.imagesblog4 {
  display: block;
  width: 100%;
  height: 700px;
}
.blog-button {
  width: 32%;
  height: 54px;
  top: 350px;
  position: absolute;
  left: 67%;
  color: white;
  background-color: #59260b;
  font-family: Mukta;
}
.touch {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.get-in-touch {
  text-align: center;
  padding: 20px;
  max-width: 590px;
  max-height: 399px;
  display: flex;
  flex-direction: column;
  position: relative;
  gap: 20px;
}

.get-in-touch .email-input {
  display: flex;
  justify-content: left;
  gap: 10px;
  margin-bottom: 20px;
}

.get-in-touch .email-input input {
  font-size: 14px;
  border: none;
  border-bottom: 1px solid #59260b;
  width: 70%;
  color: #c5b0aa;
  font-family: Mukta;
}

.Submit {
  padding: 14px 28px;
  font-size: 17px;
  background-color: #edebe8;
  color: black;
  border: 1px solid #59260b;
  cursor: pointer;
  position: relative;
  align-self: flex-start;
  margin-top: auto;
  font-family: Mukta;
}

.Submit:hover {
  background-color: #4a1f09;
}
.get-in-touch-text {
  font-size: 17px;
  font-weight: 300px;
  top: 40%;
  position: relative;
  text-align: left;
  font-family: Mukta;
}
.get-in-touch-text-height {
  font-size: 72px;
  font-weight: 400px;
  top: 40%;
  position: relative;
  text-align: left;
  color: #59260b;
  font-family: Marcellus;
}
.footer {
  background-color: #59260b;
  padding: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.footer-container {
  max-width: 1200px;
  width: 100%;
  position: relative;
}

.vector {
  position: absolute;
  top: 0;
  left: 0;
}

.footer-nav ul {
  list-style-type: none;
  column-count: 4;
  column-gap: 20px;
  padding: 0;
  margin: 0 auto;
  width: 80%;
}

.footer-nav ul li {
  padding: 10px 0;
  break-inside: avoid;
}

.footer-nav ul li a {
  color: white;
  text-decoration: none;
  opacity: 0.7;
  transition: opacity 0.5s;
  font-size: 17px;
  font-family: Mukta;
}

.footer-nav ul li a:hover {
  opacity: 1;
}

.footer-bottom {
  color: white;
  padding: 10px;
  text-align: center;
  margin-top: 20px;
  font-family: Mukta;
}
@media (max-width: 1220px) {
  .image-wrapper {
    width: 45%;
  }
  .image-wrapper1 {
    width: 40%;
  }
  .image-wrapper1:nth-child(1) {
  }

  .image-wrapper1:nth-child(2) {
    width: 23%;
  }

  .image-wrapper1:nth-child(3) {
    width: 32%;
  }
  .image-wrapper1:nth-child(4) {
    width: 57%;
  }
}
@media (max-width: 1000px) {
  .header-title {
    font-size: 42px;
    width: 470px;
  }
  .header-button {
    margin: 5% 1% 5%;
  }
  .txtcontainer {
    margin: 5% 5%;
  }
  .txt1 {
    font-size: 48px;
  }
  .txt2 {
    font-size: 36px;
  }
  .image-wrapper {
    width: 40%;
  }
  .image-wrapper1 {
    width: 40%;
  }
  .header-title {
    padding-left: 1%;
  }
  .large-image {
    position: absolute;
    top: 110px;
    left: 50%;
    width: 48%;
    height: auto;
  }

  .small-image {
    position: absolute;
    top: 474px;
    left: 40%;
    width: 30%;
    height: auto;
  }
  @media (max-width: 768px) {
    .large-image {
      display: none;
    }

    .small-image {
      display: none;
    }

    .header-down {
      height: auto;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .container {
      padding-top: 0;
      align-items: center;
      text-align: center;
    }

    .header-title {
      font-size: 32px;
    }

    .header-button {
      margin: 20px 0;
    }

    .txtcontainer {
      margin: 0;
      border: none;
    }

    .txt1 {
      font-size: 36px;
    }

    .txt2 {
      font-size: 18px;
    }
    .catalogue-title {
      font-size: 45px;
      width: 100%;
    }
    .container {
      width: 100%;
    }
    .header-title {
      width: 100%;
    }
  }
}
<style scoped > .list {
  background-color: #edebe8;
  padding: 20px;
  position: relative;
}
.popular-flavors {
  margin: 0 auto;
  height: 120px;
  text-align: center;
  font-size: 48px;
  font-weight: 400;
}

.list-container {
  position: relative;
  z-index: 1;
}

.scroll-container {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.card-line {
  display: flex;
  gap: 50px;
  overflow-x: hidden;
  scroll-behavior: smooth;
  padding: 20px 0;
  width: 64%;
}

.card-container {
  border: 1px solid #c5b0aa;
  position: relative;
  flex: 0 0 auto;
  width: 250px;
}

.card-text {
  text-align: center;
  padding: 10px;
  font-family: Mukta;
}

.card-image {
  position: absolute;
  top: 10px;
  right: 10px;
  z-index: 1;
  cursor: pointer;
}
.card-image img {
  transition: transform 0.3s ease, opacity 0.3s ease;
}

.heart-animation {
  animation: heartBeat 0.5s ease;
}

@keyframes heartBeat {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}

.scroll-button {
  background-color: rgba(0, 0, 0, 0.5);
  border: none;
  color: white;
  font-size: 24px;
  cursor: pointer;
  padding: 10px;
  z-index: 2;
  position: relative;
  top: 50%;
  transform: translateY(-50%);
  margin: 10px;
}

.scroll-button.left {
  left: 0px;
}

.scroll-button.right {
  right: 0px;
}

.indicators {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}

.indicator {
  width: 30px;
  height: 3px;
  background-color: #c5b0aa;
  cursor: pointer;
  transition: background-color 0.3s;
}

.indicator.active {
  background-color: #59260b;
}
.card-main-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
@media (max-width: 1000px) {
  .scroll-button {
    display: none;
  }

  .card-line {
    overflow-x: auto;
    width: 100%;
  }

  .card-container {
    width: 200px;
  }
}
@media (max-width: 480px) {
  .footer-nav ul {
    list-style-type: none;
    column-count: 2;
    column-gap: 20px;
    padding: 0;
    margin: 0 auto;
    width: 80%;
  }
  .vector {
    position: relative;
    margin: 0 auto;
    justify-content: center;
  }
  .vectorimg {
    margin: 0 auto;
    left: 50%;
    position: relative;
  }
  .footer {
    padding: 10px;
  }
  .photo {
    display: none;
  }
  .get-in-touch-text-height {
    font-size: 36px;
    text-align: center;
  }
}
.card-container {
  position: relative;
  overflow: hidden;
}

.card-main-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: opacity 0.3s ease;
}
.card-container:hover .card-main-image {
  opacity: 0.5;
}

.card-container:hover .add-to-bag {
  opacity: 1;
  visibility: visible;
}

.add-to-bag {
  position: absolute;
  margin: 100px auto;
  left: 50%;
  transform: translateX(-50%);
  background: white;
  color: black;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
  border: 1px solid #59260b;
}

.lock-icon {
  position: absolute;
  top: 0px;
  right: 20px;
  width: 14px;
  height: 16px;
  display: none;
}

@media (max-width: 1000px) {
  .card-container:hover .card-main-image {
    opacity: 1;
  }

  .card-container:hover .add-to-bag {
    opacity: 0;
    visibility: hidden;
  }

  .lock-icon {
    display: block;
  }
}
</style>
