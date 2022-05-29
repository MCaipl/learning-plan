<template>
  <div class="outer select-none group">
    <div class="image-wrapper w-full relative overflow-hidden">
      <img class="group-hover:scale-125 transition-all duration-500 ease-in-out transform" :src="image" alt="" loading=lazy>
      <div class="absolute left-0 top-0 h-full w-full bg-gradient-to-t from-black to-transparent"></div>
      <div class="absolute left-0 top-0 visible group-hover:invisible">
        <slot name="tl">
        </slot>
      </div>
      <div class="absolute right-0 top-0 visible group-hover:invisible">
        <slot name="tr">

        </slot>
      </div>
      <div class="absolute left-0 bottom-0 visible group-hover:invisible">
        <slot name="bl">
        </slot>
      </div>
      <div class="absolute right-0 bottom-0 visible group-hover:invisible">
        <slot name="br"></slot>
      </div>
      <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 invisible group-hover:visible">
        <slot name="center">
          <Icon name="bi:play-circle" width="w-12" height="h-12" class="text-white"/>
        </slot>
      </div>
    </div>
    <div class="text-wrapper">
      <slot name="text"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["image"],
  setup(props) {
    const backgroundImageComponent = resolveComponent('TeamClash')

    return {
      backgroundImageComponent
    }
  }
};
</script>