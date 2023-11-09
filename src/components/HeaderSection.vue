<script setup>
import { headerNav } from "@/constants/index";


// import { ref, onMounted } from 'vue';

// const link = () => {
//   document.querySelectorAll("a[href^='#']").forEach((anchor) => {
//     anchor.addEventListener("click", function (e) {
//       e.preventDefault();

//       const targetId = this.getAttribute("href");
//       const targetElement = document.querySelector(targetId);

//       if (targetElement) {
//         targetElement.scrollIntoView({ behavior: "smooth" });
//       }
//     });
//   });
// };

// onMounted(() => {
//   link();
// });

</script>

<template>
      <header id="header" role="banner">
    <div class="header_inner">
      <div class="header_logo">
        <a href="#">portfolio <em>vite</em></a>
      </div>
      <div class="header_nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
        <ul>
            <li v-for="(nav, key) in headerNav" :key="key">
                <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
            </li>
        </ul>
      </div>
      <div class="header_nav_mobile" id="headerToggle" aria-controls="primary-menu" aria-expanded="isNavVisible.toString()" role="button" @click="toggleMobileMenu">
        <span></span>
      </div>
    </div>
  </header>
  <!-- //header -->
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible;
        },
        scrollLink(event) {
            event.preventDefault();

            const targetId = event.target.getAttribute("href");
            const targetElement = document.querySelector(targetId);

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: "smooth" });
            }
        },
    },
};
</script>

<style lang="scss">
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 1000;

    /* display: none; */
}

.header_inner {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: var(--black);
    color: var(--white);
    padding: 1rem;
}

.header_logo {
    font-size: 1.8rem;
    text-align: center;
    font-family: var(--chan);
    text-transform: uppercase;
    line-height: 1.1;
}
.header_logo em {
    display: block;
    font-size: 0.5rem;
    color: var(--mainBg-color);
}
.header_logo a {}
.header_logo a:hover {
    color: var(--mainBg-color);
}

.header_nav {}

.header_nav li {
    display: inline;
}

.header_nav li a {
    margin: 0 10px; 
    text-transform: uppercase;
    font-family: var(--pay);
    position: relative;
}
.header_nav li a::before {
    content: '';
    /* width: calc(100% - 30px); */
    width: 100%;
    height: 1px;
    background-color: var(--mainBg-color);
    position: absolute;
    left: 0;
    bottom: 0;
    transform: scaleX(0);
    transition: all 0.3s;
}
.header_nav li a:hover::before {
    transform: scaleX(1);
}

.header_nav_mobile {
    width: 40px;
    height: 40px;
    cursor: pointer;
    display: none;
}

.header_nav_mobile span {
    display: block;
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    margin-top: 19px;
    position: relative;
}

.header_nav_mobile span::before {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    position: absolute;
    right: 0;
    top: 6px;
    transition: width 0.3s;
}

.header_nav_mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainBg-color);
    position: absolute;
    left: 0;
    bottom: 6px;
    transition: width 0.3s;
}

@media (max-width: 800px) {
    .header_nav {
        display: none;
    }
    .header_nav.show {
        display: block;
    }
    .header_nav.show ul {
        display: block;
        position: absolute;
        right: 0;
        top: 68px;
        background-color: #ffd90081;
        z-index: 10000;
        min-width: 150px;
        padding: 20px 0;
    }
    .header_nav.show li {
        display: block;
        text-align: right;
        color: var(--black);
    }
    .header_nav.show li a {
        display: inline-block;
        padding: 10px 0;
    }
    .header_nav.show + .header_nav_mobile span::before {
        width: 20px;
    }
    .header_nav.show + .header_nav_mobile span::after {
        width: 20px;
    }

    .header_nav_mobile {
        display: block;
    }
}
</style>