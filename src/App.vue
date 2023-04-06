<template>
  <div class="navigation">
    <img :src="logo" />
    <div class="navigation__menu">
      <ul class="navigation__list">
        <li class="navigation__item"><a href="">Home</a></li>
        <li class="navigation__item"><a href="">About</a></li>
        <li class="navigation__item"><a href="">Contact</a></li>
        <li class="navigation__item"><a href="">Blog</a></li>
        <li class="navigation__item"><a href="">Careers</a></li>
      </ul>
      <button>Request Invite</button>
    </div>
    <div class="sidemenu">
      <button
        class="sidemenu__btn"
        @click="navOpen = !navOpen"
        :class="{ active: navOpen }"
      >
        <span class="top"></span>
        <span class="mid"></span>
        <span class="bottom"></span>
      </button>
      <transition name="translateX">
        <nav v-show="navOpen">
          <div class="sidemenu__wrapper">
            <ul class="sidemenu__list">
              <li class="sidemenu__item"><a href="">Home</a></li>
              <li class="sidemenu__item"><a href="">About</a></li>
              <li class="sidemenu__item"><a href="">Contact</a></li>
              <li class="sidemenu__item"><a href="">Blog</a></li>
              <li class="sidemenu__item"><a href="">Careers</a></li>
            </ul>
          </div>
        </nav>
      </transition>
    </div>
  </div>
  <div class="conteiner">
    <div class="conteiner-home">
      <img :src="phones" alt="" />
      <div class="holder">
        <h1>Next generation digital banking</h1>
        <p>
          Take your financial life online. Your Easybank account will be a
          one-stop-shop for spending, saving, budgeting, investing, and much
          more
        </p>
        <button>Request Invite</button>
      </div>
    </div>
    <div class="conteiner-about">
      <h1>Why choose Easybank?</h1>
      <p>
        We leverage Open Banking to turn your bank account into your financial
        hub. Control your finances like never before.
      </p>
      <div class="aboutHolder">
        <div>
          <img :src="imagesForAbout[0]" alt="" />
          <h2>{{ About[0] }}</h2>
          <p>
            Our modern web and mobile applications allow you to keep track of
            your finances wherever you are in the world.
          </p>
        </div>
        <div>
          <img :src="imagesForAbout[1]" alt="" />
          <h2>{{ About[1] }}</h2>
          <p>
            See exactly where your money goes each month. Receive notifications
            when you’re close to hitting your limits.
          </p>
        </div>
        <div>
          <img :src="imagesForAbout[2]" alt="" />
          <h2>{{ About[2] }}</h2>
          <p>
            We don’t do branches. Open your account in minutes online and start
            taking control of your finances right away.
          </p>
        </div>
        <div>
          <img :src="imagesForAbout[3]" alt="" />
          <h2>{{ About[3] }}</h2>
          <p>
            Manage your savings, investments, pension, and much more from one
            account. Tracking your money has never been easier.
          </p>
        </div>
      </div>
    </div>

    <div class="conteiner-articles">
      <h1>Lastest Articles</h1>
      <div class="articlesHolder">
        <div>
          <img :src="iamgesForArticles[0]" alt="" />
          <span>{{ articles[0] }}</span>
          <h2>Receive money in any currency with no fees</h2>
          <p>
            The world is getting smaller and we’re becoming more mobile. So why
            should you be forced to only receive money in a single …
          </p>
        </div>

        <div>
          <img :src="iamgesForArticles[1]" alt="" />
          <span>{{ articles[1] }}</span>
          <h2>Treat yourself without worrying about money</h2>
          <p>
            Our simple budgeting feature allows you to separate out your
            spending and set realistic limits each month. That means you …
          </p>
        </div>

        <div>
          <img :src="iamgesForArticles[2]" alt="" />
          <span>{{ articles[0] }}</span>
          <h2>Take your Easybank card wherever you go</h2>
          <p>
            We want you to enjoy your travels. This is why we don’t charge any
            fees on purchases while you’re abroad. We’ll even show you …
          </p>
        </div>

        <div>
          <img :src="iamgesForArticles[3]" alt="" />
          <span>{{ articles[1] }}</span>
          <h2>Our invite-only Beta accounts are now live!</h2>
          <p>
            After a lot of hard work by the whole team, we’re excited to launch
            our closed beta. It’s easy to request an invite through the site ...
          </p>
        </div>
      </div>
    </div>

    <div class="conteiner-contact">
      <img class="logo" :src="logo" />
      <div class="holderIcon">
        <img v-for="item in icons" :key="item.icon" :src="item.icon" alt="" />
      </div>
      <h3>{{ info[0] }}</h3>
      <h3>{{ info[1] }}</h3>
      <h3>{{ info[2] }}</h3>
      <h3>{{ info[3] }}</h3>
      <h3>{{ info[4] }}</h3>
      <h3>{{ info[5] }}</h3>
      <h3>{{ info[6] }}</h3>
      <button>Request Invite</button>
      <span>© Easybank. All Rights Reserved</span>
    </div>
  </div>
</template>

<script>
import logo from "./assets/logo.svg";
import phones from "./assets/image-mockups.png";
import online from "./assets/icon-online.svg";
import budgeting from "./assets/icon-budgeting.svg";
import onboarding from "./assets/icon-onboarding.svg";
import api from "./assets/icon-api.svg";
import currency from "./assets/image-currency.jpg";
import restaurant from "./assets/image-restaurant.jpg";
import plane from "./assets/image-plane.jpg";
import confetti from "./assets/image-confetti.jpg";

export default {
  name: "App",
  components: {},
  data() {
    return {
      logo: logo,
      phones: phones,
      imagesForAbout: [online, budgeting, onboarding, api],
      iamgesForArticles: [currency, restaurant, plane, confetti],
      articles: ["By Claiere Robinson", "By Wilson Huttson"],
      el: "#sidemenu",
      icons: [
        {
          icon: require("./assets/icon-facebook.svg"),
        },
        {
          icon: require("./assets/icon-youtube.svg"),
        },
        {
          icon: require("./assets/icon-twitter.svg"),
        },
        {
          icon: require("./assets/icon-pinterest.svg"),
        },
        {
          icon: require("./assets/icon-instagram.svg"),
        },
      ],
      info: [
        "About Us",
        "Contact",
        "Blog",
        "Careers",
        "Support",
        "Private Policy",
      ],
      navOpen: false,
      About: [
        "Online Banking",
        "Simple Budgeting",
        "Fast Onboarding",
        "Open API",
      ],
    };
  },
};
</script>

<style lang="scss">
@import "/styles/global.scss";
</style>
