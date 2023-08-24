<template>
  <div b="solid 10 #f8f8f8">
    <div class="bg-#f8f8f8">
        <h2 class="text-center text-1rem">{{ roomType.name }}</h2>
    </div>
    <div class="p-1rem">
      <!--平假旺 -->
      <div flex="~ justify-between">
        <div 
        v-for="(dateType, i) in dateTypes" 
        :key="dateType"
        >
        <div flex="~ col items-center">
          <span>{{ dateType }}</span>
          <div>
            <el-input-number
              v-model="priceArr[i]"
              :min="1"
              :controls="false"
            />
          </div>
        </div>
      </div>
      </div> 
      <hr class="my-1rem">
      <slot />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  roomType: {
    type: Object,
    default: () => ({})
  }
})

const { priceArr } = toRefs(props.roomType) 

const dateTypes = [
  '平日',
  '假日',
  '旺日'
]
</script>
<style scoped>
::v-deep() {
  .el-input-number {
    width: auto;
  }
}
</style>