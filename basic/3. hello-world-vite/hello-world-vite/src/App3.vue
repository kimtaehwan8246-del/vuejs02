<template>
  <div id="date1">
    {{ date }}
  </div>
  <div id="date2">
    {{ date2 }}
  </div>
</template>

<script>
export default {
  setup() {
    const date = Date().toString();
    return {
      data,
    };
  },

  data() {
    return {
      data2: Date().toString(),
    };
  },
};
</script>
