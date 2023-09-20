<template>
    <section class="w-full overflow-hidden bg-cover bg-center h-96 flex"
      :style="{ backgroundImage: 'url(' + highlightedShow?.image?.original + ')' }">
      <div v-if="showInfo"
        class="p-5 bg-white bg-opacity-10 backdrop-blur flex flex-col justify-end text-lg font-bold text-white min-w-8">
        <router-link :to="'/show/' + highlightedShow.id" class="text-lg sm:text-2xl pb-2 font-bold">
        {{ highlightedShow.name }}
      </router-link>
      <div>{{ highlightedShow.runtime }}m - {{ highlightedShow.language }}</div>
      <div>{{ highlightedShow.genres?.join(', ') }}</div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BillboardItem',
  props: {
    highlightedShow: {
      type: Object,
      required: true,
    },
    showInfo: {
      type: Boolean,
      required: false,
    }
  },
};
</script>