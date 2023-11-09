<script setup>
import {portText} from "@/constants/index"
</script>

<template>
    <section id="port">
      <div class="port_inner">
        <h2 class="port_title">
          portfolio <em>포폴 작업물</em>
        </h2>
        <div class="port_wrap">
          <div class="port_item" :class="'p' + (key + 1)" v-for="(port, key) in portText" :key="key">
            <span class="num">{{ port.num }}.</span>
            <a href="#">
              <img :src="port.img" alt="">
            </a>
            <h3 class="title">{{ port.title }}</h3>
            <p class="desc">
              {{ port.desc }}
            </p>
            <a :href="port.view" class="btn">사이트 보기</a>
          </div>
        </div>
      </div>
    </section>
    <!-- //port -->
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
    mounted: function(){
        this.scrollAnimaion();
    },
    methods: {
        scrollAnimaion() {
            const horSection = gsap.utils.toArray(".port_item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top 56px",
                    end: "+=3000",
                    pin: true,
                    scrub: 1,
                    markers: true,
                    invalidateOnRefresh: true,
                    anticipatePin: 1,
                }
            });
        }
    }
}
</script>

<style lang="scss">
#port {
    width: 100%;
    overflow: hidden;
}
.port_inner {
    padding: 16px;
}
.port_title {
    position: sticky;
    top: 60px;
    left: 0;
    width: 80%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--mainPop-font);
    border-bottom: 0.4vw solid var(--black);
    color: var(--black);
    margin-bottom: 7vw;
    background-color: var(--mainBg-color);
}
.port_title em {
    font-family: var(--mainKor-font);
    font-size: 1.5rem;
    font-weight: 400;
    vertical-align: 4px;
}
.port_wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
    /* position: relative; */
}
.port_item {
    width: 500px;
    background-color: var(--black);
    margin-right: 20px;
    padding: 30px;
}
.port_item:nth-child(2n) {
    background-color: var(--black100);
}
.port_item:nth-child(3n) {
    background-color: var(--black300);
}
.port_item .num {
    font-size: 2vw;
    line-height: 1;
    font-weight: 900;
    font-family: var(--mainNum-font);
    color: var(--mainBg-color);
    display: block;
    padding-bottom: 10px;
}
.port_item a {
    display: flex;
    align-items: center;
    justify-content: center;
    
}
.port_item img {
    /* width: 400px; */
    width: 100%;
    height: 250px;
    background-color: var(--black);
    border-radius: 5px;
    /* filter: opacity(0.2); */
    filter:grayscale(1);
    border: 5px solid var(--black);
}
.port_item img:hover {
    filter:grayscale(0);
    transition: all 0.3s;
    border: 5px solid var(--mainBg-color);
}
.port_item .title {
    color: var(--white);
    font-size: 1.7rem;
    border-bottom: 3px solid var(--mainBg-color);
    padding: 10px 0;
    text-align: center;
}
.port_item .desc {
    color: var(--white);
    padding-top: 20px;
    font-size: 1.2rem;
}
.port_item .btn {
    border: 1px solid var(--mainBg-color);
    margin: 20px 0 25px 0;
    padding: 10px;
    color: var(--white500);
}
</style>