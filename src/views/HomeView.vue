<template>
  <div class="scene-try">
    <Scene
      :pano="scene.pano"
      :position="scene.position"
      :rotation="scene.rotation"
      :links="scene.links"
    >
    </Scene>
  </div>
</template>

<script>
// eslint-disable-next-line
import { Scene } from "vuejs-vr";
export default {
  components: {
    Scene,
  },
  data: () => ({
    scene: {
      pano: {
        source: "/faces/pano_%s.jpg",
        type: "cube",
      },
      position: {
        x: 0,
        y: 0,
        z: 0,
      },
      rotation: {
        x: 0,
        y: (135.0 * Math.PI) / 180.0,
        z: 0,
      },
      links: [
        {
          sceneId: "scene1",
          position: {
            x: 100,
            y: 0,
            z: -100,
          },
        },
        {
          sceneId: "scene2",
          position: {
            x: 200,
            y: 0,
            z: -20,
          },
        },
      ],
    },
  }),
};
</script>

<style lang="scss" scoped>
.scene-try {
  height: 500px;
  width: 100%;
  border: 5px solid burlywood;
  box-sizing: border-box;
}
</style>
