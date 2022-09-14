<template>
  <div id="hero">
    <h1>Moi c'est Alex 👋</h1>
    <h2>Je développe toutes sortes de choses sur le web.</h2>

    <p class="intro">
      Je suis un Développeur Web spécalisé dans la conception d'application
      authentique et sur-mesure. Et tout ça, avec passion. 😄
    </p>

    <Code :codes="lineCode" />
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";
import Buttton from "./Buttton.vue";
import Code from "./Code.vue";
import { gsap } from "gsap";

export default defineComponent({
  setup() {
    const lineCode = {
      1: {
        id: 1,
        space: 0,
        text: "class <b>Person</b> {",
      },
      2: {
        id: 2,
        space: 1,
        text: "constructor() {",
      },
      3: {
        id: 3,
        space: 2,
        text: "<b>this</b>.name = <t>'Alex Salim'</t>",
      },
      4: {
        id: 4,
        space: 2,
        text: "<b>this</b>.languages = [<t>'Javascript'</t>, <t>'Typescript'</t>, <t>'VueJS'</t>, <t>'Nuxt'</t>, <t>'Sass'</t>] <comment>// Et bien plus !</comment>",
      },
      5: {
        id: 5,
        space: 2,
        text: "<b>this</b>.age = <b>new</b> Date().getFullYear() - <b>new</b> Date(<t>'07/18/1998'</t>).getFullYear()",
      },
      6: {
        id: 6,
        space: 2,
        text: "<b>this</b>.hobbies = [<t>'Programmation'</t>, <t>'Jujitsu'</t>, <t>'Musique'</t>]",
      },
      7: {
        id: 7,
        space: 1,
        text: "}",
      },
      8: {
        id: 8,
        space: 0,
        text: "}",
      },
    };

    onMounted(() => {
      const tl = gsap.timeline();

      tl.from("#hero h1", {
        y: -100,
        opacity: 0,
        duration: 0.3,
      })
      .from("#hero h2", {
        y: -100,
        opacity: 0,
        duration: 0.3,
      })
      .from("#hero .intro", {
        y: -100,
        opacity: 0,
        duration: 0.3
      })
      .from("#hero .codeblock", {
        x: -100,
        opacity: 0,
        duration: 0.3
      });
    });

    return { lineCode };
  },
  components: { Buttton, Code },
});
</script>
