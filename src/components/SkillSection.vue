<script setup>
import {skillText} from "@/constants/index"
</script>

<template>
    <section id="skill">
      <div class="skill_inner">
        <h2 class="skill_title">
          challenge <em>나의 도전</em>
        </h2>
        <div class="skill_desc">
          <div v-for="(skill, key) in skillText" :key="key">
            <span>{{ key+1 }}.</span>
            <h3>{{ skill.title }}</h3>
            <p>
              {{ skill.desc }}
            </p>
          </div>
        </div>
      </div>
    </section>
    <!-- //skill -->
</template>
<style lang="scss">
.skill_inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;
}
.skill_title {
    position: sticky;
    top: 60px;
    left: 0;
    width: 48%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 900;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--mainPop-font);
    border-bottom: 0.4vw solid var(--black);
    color: var(--black);
}
.skill_title em {
    font-family: var(--mainKor-font);
    font-size: 1.5rem;
    font-weight: 400;
    display: inline-block;
    vertical-align: 4px;
}
.skill_desc {
    width: 50%;
}
.skill_desc span {
    font-size: 5vw;
    line-height: 1.5;
    font-weight: 900;
    font-family: var(--mainNum-font);
    color: var(--black);
}
.skill_desc h3 {
    font-size: 1.9rem;
    text-decoration: underline;
    text-underline-position: under;
    margin-bottom: 1vw;
    color: var(--black);
}
.skill_desc p {
    margin-bottom: 30vh;
    font-size: 1.5rem;
    font-family: var(--mainKor-font);
    color: var(--black);
}

@media (max-width:800px){
    .skill_inner {
        flex-direction: column;
    }
    .skill_title {
        width: 100%;
        font-size: 6vw;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
        border-bottom: 0.8vw solid var(--black);
    }
    .skill_desc {
        width: 100%;
    }
    .skill_desc span {
        font-size: 20vw;
    }
    .skill_desc h3 {
        font-size: 24px;
        margin-bottom: 2vw;
    }
}
</style>