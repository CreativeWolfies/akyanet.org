<template>
  <picture>
    <source
      v-for="img in sortedSrcSetWithoutSmallest"
      :srcset="srcSetText(img.url, img.indicator)"
      :media="mediaText(img.minWidth)"
    />
    <img
      :src="require(smallestImgSrc)"
      :title="title"
      :alt="alt"
      :width="smlstWidth"
      :height="smlstHeight"
    />
  </picture>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    },
    imgSet: {
      type: Array,
      required: true
    },
    smlstWidth: {
      type: Number,
      required: false
    },
    smlstHeight: {
      type: Number,
      required: false
    }
  },
  methods: {
    srcSetText(imgUrl, indicator) {
      return indicator === undefined ? imgUrl : `${imgUrl} ${indicator}`;
    },
    mediaText(minWidth) {
      return minWidth !== undefined ? `(min-width: ${minWidth}px)` : undefined;
    }
  },
  computed: {
    sortedSrcSet() {
      return this.imgSet.sort(({minWidth: minWA}, {minWidth: minWB}) => minWA < minWB);
    },
    sortedSrcSetWithoutSmallest() {
      return this.sortedSrcSet.slice(0, this.sortedSrcSet.length - 2);
    },
    smallestImgSrc() {
      return this.sortedSrcSet.slice(this.sortedSrcSet.length - 1);
    }
  }
};
</script>
