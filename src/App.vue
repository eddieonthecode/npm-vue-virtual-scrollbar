<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue';

import HelloWorld from './components/HelloWorld.vue';
import VueVirtualScrollbar from '../lib/VueVirtualScrollbar.vue';
const scroll = ref();
const scroll2 = ref();
const target = ref<any>();
const count = ref<number>(1);

function setScroll() {
  if (count.value % 2) {
    target.value = scroll.value;
  } else {
    target.value = scroll2.value;
  }
  count.value++;
}

function positionChanged(newPosition) {
  console.log(newPosition);
}
</script>

<template>
  <button @click="setScroll">Toggle Scroll</button>
  <div style="position: relative">
    <div
      ref="scroll"
      id="scrollable"
      class="scrollable"
      style="margin-right: 10px"
    >
      <div class="scrollable__content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis
        ultrices odio. Etiam laoreet hendrerit tellus vel vestibulum. Nulla id
        tempor nunc. Aliquam erat volutpat. Phasellus a vulputate sem. Proin
        vitae euismod risus, eget ultricies justo. Lorem ipsum dolor sit amet,
        consectetur adipiscing elit. Proin lacinia arcu quis libero posuere, eu
        iaculis justo sagittis. Fusce malesuada eu sapien pellentesque maximus.
        Praesent suscipit hendrerit augue, id suscipit risus iaculis in. Donec
        in ultrices sem. Curabitur dapibus enim sed mattis mollis. Integer sit
        amet porttitor metus, at dictum neque. Morbi a sollicitudin lectus.
        Quisque diam urna, pellentesque non posuere eu, fringilla at magna.
        Phasellus finibus vitae ante at viverra. Nam at iaculis orci, eu
        accumsan diam. Aenean vestibulum at ipsum vel gravida. Nunc nec ante
        eget nunc ultrices eleifend. Class aptent taciti sociosqu ad litora
        torquent per conubia nostra, per inceptos himenaeos. Suspendisse eget
        nisl ac est posuere placerat vulputate id est. Aliquam erat volutpat.
        Donec sed tellus scelerisque dui cursus fermentum in et ex. Curabitur
        nec feugiat nibh, in pellentesque diam. Duis porta, mi id suscipit
        imperdiet, neque massa elementum ex, sed volutpat diam augue eu ipsum.
        Sed consectetur dolor sit amet bibendum malesuada. Mauris ultricies
        justo sed pellentesque condimentum. Mauris vel rutrum quam. Pellentesque
        ornare orci felis, id pellentesque velit aliquet in. Duis rutrum tortor
        eu tincidunt facilisis. Ut dictum erat a leo blandit, et gravida purus
        varius. Phasellus dictum mauris ac purus pharetra lobortis. Nam vehicula
        sapien in nunc suscipit euismod. Nunc sed pharetra quam, dictum iaculis
        ante. Integer vitae nunc libero. Nulla at augue fringilla, blandit dolor
        ac, lobortis leo. Nulla non sem sed lacus porttitor dapibus. Suspendisse
        imperdiet tortor dui, bibendum gravida quam ultricies ut. Nam pharetra
        semper mauris eget ullamcorper. Donec at convallis libero. Cras pulvinar
        laoreet tortor, id efficitur felis luctus ac. Suspendisse sollicitudin
        tempor est, condimentum posuere ipsum efficitur vitae. Donec congue
        lorem sit amet bibendum ornare. Nunc placerat, lectus vitae venenatis
        posuere, dolor dolor blandit ipsum, at consectetur tellus velit vel sem.
        Vestibulum nec nulla tellus. Proin ullamcorper ultricies bibendum.
        Curabitur magna nisl, finibus quis gravida ac, pretium at ipsum. Nam
        cursus neque magna, sed accumsan elit viverra a. Lorem ipsum dolor sit
        amet, consectetur adipiscing elit. Maecenas quis ultrices odio. Etiam
        laoreet hendrerit tellus vel vestibulum. Nulla id tempor nunc. Aliquam
        erat volutpat. Phasellus a vulputate sem. Proin vitae euismod risus,
        eget ultricies justo. Lorem ipsum dolor sit amet, consectetur adipiscing
        elit. Proin lacinia arcu quis libero posuere, eu iaculis justo sagittis.
        Fusce malesuada eu sapien pellentesque maximus. Praesent suscipit
        hendrerit augue, id suscipit risus iaculis in. Donec in ultrices sem.
        Curabitur dapibus enim sed mattis mollis. Integer sit amet porttitor
        metus, at dictum neque. Morbi a sollicitudin lectus. Quisque diam urna,
        pellentesque non posuere eu, fringilla at magna. Phasellus finibus vitae
        ante at viverra. Nam at iaculis orci, eu accumsan diam. Aenean
        vestibulum at ipsum vel gravida. Nunc nec ante eget nunc ultrices
        eleifend. Class aptent taciti sociosqu ad litora torquent per conubia
        nostra, per inceptos himenaeos. Suspendisse eget nisl ac est posuere
        placerat vulputate id est. Aliquam erat volutpat. Donec sed tellus
        scelerisque dui cursus fermentum in et ex. Curabitur nec feugiat nibh,
        in pellentesque diam. Duis porta, mi id suscipit imperdiet, neque massa
        elementum ex, sed volutpat diam augue eu ipsum. Sed consectetur dolor
        sit amet bibendum malesuada. Mauris ultricies justo sed pellentesque
        condimentum. Mauris vel rutrum quam. Pellentesque ornare orci felis, id
        pellentesque velit aliquet in. Duis rutrum tortor eu tincidunt
        facilisis. Ut dictum erat a leo blandit, et gravida purus varius.
        Phasellus dictum mauris ac purus pharetra lobortis. Nam vehicula sapien
        in nunc suscipit euismod. Nunc sed pharetra quam, dictum iaculis ante.
        Integer vitae nunc libero. Nulla at augue fringilla, blandit dolor ac,
        lobortis leo. Nulla non sem sed lacus porttitor dapibus. Suspendisse
        imperdiet tortor dui, bibendum gravida quam ultricies ut. Nam pharetra
        semper mauris eget ullamcorper. Donec at convallis libero. Cras pulvinar
        laoreet tortor, id efficitur felis luctus ac. Suspendisse sollicitudin
        tempor est, condimentum posuere ipsum efficitur vitae. Donec congue
        lorem sit amet bibendum ornare. Nunc placerat, lectus vitae venenatis
        posuere, dolor dolor blandit ipsum, at consectetur tellus velit vel sem.
        Vestibulum nec nulla tellus. Proin ullamcorper ultricies bibendum.
        Curabitur magna nisl, finibus quis gravida ac, pretium at ipsum. Nam
        cursus neque magna, sed accumsan elit viverra a.
      </div>
    </div>

    <VueVirtualScrollbar
      :horizontal="true"
      target="#scrollable"
      @positionChanged="positionChanged"
    ></VueVirtualScrollbar>
    <VueVirtualScrollbar
      style="position: absolute; top: 0; bottom: 0; right: 0"
      :horizontal="false"
      :target="target"
    ></VueVirtualScrollbar>
  </div>
  <div
    ref="scroll2"
    id="scrollable2"
    class="scrollable"
    style="margin-right: 10px"
  >
    <div class="scrollable__content">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis
      ultrices odio. Etiam laoreet hendrerit tellus vel vestibulum. Nulla id
      tempor nunc. Aliquam erat volutpat. Phasellus a vulputate sem. Proin vitae
      euismod risus, eget ultricies justo. Lorem ipsum dolor sit amet,
      consectetur adipiscing elit. Proin lacinia arcu quis libero posuere, eu
      iaculis justo sagittis. Fusce malesuada eu sapien pellentesque maximus.
      Praesent suscipit hendrerit augue, id suscipit risus iaculis in. Donec in
      ultrices sem. Curabitur dapibus enim sed mattis mollis. Integer sit amet
      porttitor metus, at dictum neque. Morbi a sollicitudin lectus. Quisque
      diam urna, pellentesque non posuere eu, fringilla at magna. Phasellus
      finibus vitae ante at viverra. Nam at iaculis orci, eu accumsan diam.
      Aenean vestibulum at ipsum vel gravida. Nunc nec ante eget nunc ultrices
      eleifend. Class aptent taciti sociosqu ad litora torquent per conubia
      nostra, per inceptos himenaeos. Suspendisse eget nisl ac est posuere
      placerat vulputate id est. Aliquam erat volutpat. Donec sed tellus
      scelerisque dui cursus fermentum in et ex. Curabitur nec feugiat nibh, in
      pellentesque diam. Duis porta, mi id suscipit imperdiet, neque massa
      elementum ex, sed volutpat diam augue eu ipsum. Sed consectetur dolor sit
      amet bibendum malesuada. Mauris ultricies justo sed pellentesque
      condimentum. Mauris vel rutrum quam. Pellentesque ornare orci felis, id
      pellentesque velit aliquet in. Duis rutrum tortor eu tincidunt facilisis.
      Ut dictum erat a leo blandit, et gravida purus varius. Phasellus dictum
      mauris ac purus pharetra lobortis. Nam vehicula sapien in nunc suscipit
      euismod. Nunc sed pharetra quam, dictum iaculis ante. Integer vitae nunc
      libero. Nulla at augue fringilla, blandit dolor ac, lobortis leo. Nulla
      non sem sed lacus porttitor dapibus. Suspendisse imperdiet tortor dui,
      bibendum gravida quam ultricies ut. Nam pharetra semper mauris eget
      ullamcorper. Donec at convallis libero. Cras pulvinar laoreet tortor, id
      efficitur felis luctus ac. Suspendisse sollicitudin tempor est,
      condimentum posuere ipsum efficitur vitae. Donec congue lorem sit amet
      bibendum ornare. Nunc placerat, lectus vitae venenatis posuere, dolor
      dolor blandit ipsum, at consectetur tellus velit vel sem. Vestibulum nec
      nulla tellus. Proin ullamcorper ultricies bibendum. Curabitur magna nisl,
      finibus quis gravida ac, pretium at ipsum. Nam cursus neque magna, sed
      accumsan elit viverra a. Lorem ipsum dolor sit amet, consectetur
      adipiscing elit. Maecenas quis ultrices odio. Etiam laoreet hendrerit
      tellus vel vestibulum. Nulla id tempor nunc. Aliquam erat volutpat.
      Phasellus a vulputate sem. Proin vitae euismod risus, eget ultricies
      justo. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin
      lacinia arcu quis libero posuere, eu iaculis justo sagittis. Fusce
      malesuada eu sapien pellentesque maximus. Praesent suscipit hendrerit
      augue, id suscipit risus iaculis in. Donec in ultrices sem. Curabitur
      dapibus enim sed mattis mollis. Integer sit amet porttitor metus, at
      dictum neque. Morbi a sollicitudin lectus. Quisque diam urna, pellentesque
      non posuere eu, fringilla at magna. Phasellus finibus vitae ante at
      viverra. Nam at iaculis orci, eu accumsan diam. Aenean vestibulum at ipsum
      vel gravida. Nunc nec ante eget nunc ultrices eleifend. Class aptent
      taciti sociosqu ad litora torquent per conubia nostra, per inceptos
      himenaeos. Suspendisse eget nisl ac est posuere placerat vulputate id est.
      Aliquam erat volutpat. Donec sed tellus scelerisque dui cursus fermentum
      in et ex. Curabitur nec feugiat nibh, in pellentesque diam. Duis porta, mi
      id suscipit imperdiet, neque massa elementum ex, sed volutpat diam augue
      eu ipsum. Sed consectetur dolor sit amet bibendum malesuada. Mauris
      ultricies justo sed pellentesque condimentum. Mauris vel rutrum quam.
      Pellentesque ornare orci felis, id pellentesque velit aliquet in. Duis
      rutrum tortor eu tincidunt facilisis. Ut dictum erat a leo blandit, et
      gravida purus varius. Phasellus dictum mauris ac purus pharetra lobortis.
      Nam vehicula sapien in nunc suscipit euismod. Nunc sed pharetra quam,
      dictum iaculis ante. Integer vitae nunc libero. Nulla at augue fringilla,
      blandit dolor ac, lobortis leo. Nulla non sem sed lacus porttitor dapibus.
      Suspendisse imperdiet tortor dui, bibendum gravida quam ultricies ut. Nam
      pharetra semper mauris eget ullamcorper. Donec at convallis libero. Cras
      pulvinar laoreet tortor, id efficitur felis luctus ac. Suspendisse
      sollicitudin tempor est, condimentum posuere ipsum efficitur vitae. Donec
      congue lorem sit amet bibendum ornare. Nunc placerat, lectus vitae
      venenatis posuere, dolor dolor blandit ipsum, at consectetur tellus velit
      vel sem. Vestibulum nec nulla tellus. Proin ullamcorper ultricies
      bibendum. Curabitur magna nisl, finibus quis gravida ac, pretium at ipsum.
      Nam cursus neque magna, sed accumsan elit viverra a.
    </div>
  </div>
</template>

<style scoped lang="scss">
.scrollable {
  height: 300px;
  width: 500px;
  overflow: auto;
  &__content {
    width: 1000px;
    background: aqua;
  }
}
</style>
