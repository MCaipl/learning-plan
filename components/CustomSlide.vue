<template>
  <div class="outer grid gap-1 bg-gray-700 rounded">
    <div class="image-wrapper aspect-video w-full relative">
      <!-- <img class="object-cover" src="http://placekitten.com/500/300" alt=""> -->
      <TeamClash :left="left" :right="right"></TeamClash>
      <div class="absolute left-0 top-0">
        <slot name="tl"></slot>
      </div>
      <div class="absolute right-0 top-0">
        <slot name="tr"></slot>
      </div>
      <div class="absolute left-0 bottom-0">
        <slot name="bl"></slot>
      </div>
      <div class="absolute right-0 bottom-0">
        <slot name="br"></slot>
      </div>
      <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
        <slot name="center"></slot>
      </div>
    </div>
    <div class="text-wrapper">
      <p class="text-gray-200">An even longer title on this one</p>
      <p class="text-gray-200">An even longer title on this one</p>
      <p class="text-gray-200">An even longer title on this one</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['left', 'right']
};
</script>