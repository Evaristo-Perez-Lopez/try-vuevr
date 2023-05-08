<template>
  <section class="divisor">
    <div class="visor">
      <Tour :scenes="scenes"></Tour>
    </div>
    <div class="aux">
      <img src="@/assets/faces/pano_b.jpg" alt="" srcset="" />
      <a href="https://mudin.github.io/vue-vr/#/demo-pano">vr</a>
    </div>
  </section>
</template>

<script>
import { Tour } from "vuejs-vr";
export default {
  name: "App",
  components: { Tour },
  data: () => ({
    url: ["../assets/equirectangular.jpg", "../assets/pano.png"],
    scenes: [
      {
        key: "M4wOy2s",
        panorama: {
          source: require("@/assets/equirectangular.jpg"),
          type: "image",
        },
        x: 0,
        y: 0,
        z: 0,
        rx: 0,
        rz: 0,
        ry: 90,
        connections: ["eIm7la", "eId9l0", "fK2dL7l"],
      },
      {
        key: "eIm7la",
        panorama: {
          source: require("@/assets/faces/pano_l.jpg"),
          type: "cube",
        },
        x: 100,
        y: 0,
        z: 200,
        rx: 0,
        rz: 0,
        ry: 0,
        connections: ["M4wOy2s"],
      },
      {
        key: "eId9l0",
        panorama: {
          source: require("@/assets/faces/pano_u.jpg"),
          type: "cube",
        },
        x: 150,
        y: 0,
        z: -300,
        rx: 0,
        rz: 0,
        ry: 0,
        connections: ["M4wOy2s"],
      },
      {
        key: "fK2dL7l",
        panorama: {
          source: require("@/assets/faces/pano_d.jpg"),
          type: "cube",
        },
        x: -150,
        y: 0,
        z: -300,
        rx: 0,
        rz: 0,
        ry: 0,
        connections: ["M4wOy2s"],
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
.divisor {
  display: flex;
  flex-direction: column-reverse;
}
.visor {
  display: block;
  height: 500px;
  width: 100%;
}
.aux {
  height: 250px;
  width: 100%;
  img {
    width: 100%;
    height: 100%;
  }
}
</style>
