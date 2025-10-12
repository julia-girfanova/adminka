<template>
  <div class="app">
    <Sidebar />
    <WorkingPage />
  </div>
</template>
<script>
import Sidebar from "../components/Sidebar.vue";
import WorkingPage from "../components/WorkingPage.vue";
export default {
  components: {
    Sidebar,
    WorkingPage,
  },
};
</script>
<style>
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Thin.otf") format("opentype");
  font-weight: 100;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-ExtraLight.otf") format("opentype");
  font-weight: 200;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Light.otf") format("opentype");
  font-weight: 300;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Regular.otf") format("opentype");
  font-weight: 400;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Medium.otf") format("opentype");
  font-weight: 500;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Bold.otf") format("opentype");
  font-weight: 600;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-ExtraBold.otf") format("opentype");
  font-weight: 700;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Black.otf") format("opentype");
  font-weight: 800;
  font-style: normal;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-Heavy.otf") format("opentype");
  font-weight: 900;
  font-style: normal;
}

@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-ThinItalic.otf") format("opentype");
  font-weight: 100;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-ExtraLightItalic.otf") format("opentype");
  font-weight: 200;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-LightItalic.otf") format("opentype");
  font-weight: 300;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-RegularItalic.otf") format("opentype");
  font-weight: 400;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-MediumItalic.otf") format("opentype");
  font-weight: 500;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-BoldItalic.otf") format("opentype");
  font-weight: 600;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-ExtraBoldItalic.otf") format("opentype");
  font-weight: 700;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-BlackItalic.otf") format("opentype");
  font-weight: 800;
  font-style: italic;
}
@font-face {
  font-family: "TT Norms";
  src: url("/fonts/TTNorms-HeavyItalic.otf") format("opentype");
  font-weight: 900;
  font-style: italic;
}

body {
  margin: 0px;
  font-family: "TT Norms";
  min-height: 100vh;
  display: flex;
}
.app {
  height: 100%;
  display: flex;
}
#__nuxt {
  min-height: 100%;
  width: 100%;
}
</style>
