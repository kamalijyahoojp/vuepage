<script setup lang="ts">
import { reactive } from 'vue';

const pictures: Array<string> = [
    "/photo/IMG_9691-2.JPG",
    "/photo/IMG_9693-1.JPG",
    "/photo/IMG_9694-1.JPG",
    "/photo/IMG_9697-2.JPG",
    "/photo/IMG_9699-1.JPG",
    "/photo/IMG_9701-1.JPG",
    "/photo/IMG_9703-1.JPG",
    "/photo/IMG_9705-1.JPG",
    "/photo/IMG_9707-1.JPG",
    "/photo/IMG_9709-1.JPG",
    "/photo/IMG_9710-1.JPG",
    "/photo/IMG_9714-1.JPG"
];
const listData: Array<[string, string]> = [
  ['全体写真', pictures[0] ],
  ['1組', pictures[1] ],
  ['2組', pictures[2] ],
  ['3組', pictures[3] ],
  ['4組', pictures[4] ],
  ['5組', pictures[5] ],
  ['6組', pictures[6] ],
  ['7組', pictures[7] ],
  ['Other1', pictures[8] ],
  ['Other2', pictures[9] ],
  ['Other3', pictures[10] ],
  ['Other4', pictures[11] ],
];
const wk = reactive({
  picNo: -1 as number,
});
</script>

<template>
  <h2>2025 写真</h2><br />
  <dl>
    <template v-for="(item, index) in listData" :key="index">
      <dt>{{ item[0] }}
        <button @click="wk.picNo = index">表示</button>
        <button @click="wk.picNo = -1">閉じる</button>
        <a :href="item[1]">ダイレクト表示</a>←右クリックでダウンロードできます。
      </dt>
      <dd style="display: block;">
        <img v-if="wk.picNo == index" :src="item[1]" :alt="item[0]" style="width: 1152px; height: auto;" />
      </dd>
    </template>
  </dl>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
