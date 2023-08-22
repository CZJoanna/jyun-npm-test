<template>
  <div class="p-1rem">
    <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-1rem">
    <div 
      v-for="roomType in roomTypes"
      :key="roomType"
      class="b-10 b-solid b-#f8f8f8"
    >
      <div class="bg-#f8f8f8">
       <h2 class="text-center text-1rem">{{ roomType }}</h2>
      </div>
      <div class="p-1rem">
        <!--平假旺 -->
        <div class="flex flex-justify-between">
          <div class="flex flex-col flex-items-center">
            <span>平日</span>
            <div>
              <el-input-number
                v-model="num"
                :min="1"
                :controls="false"
                @change="handleChange"
              />
            </div>
          </div>
          <div class="flex flex-col flex-items-center">
            <span>假日</span>
            <div>
              <el-input-number
                v-model="num"
                :min="1"
                controls-position="right"
                :controls="false"
                @change="handleChange"
              />
            </div>
          </div>
          <div class="flex flex-col flex-items-center">
            <span>旺日</span>
            <div>
              <el-input-number
                v-model="num"
                :min="1"
                controls-position="right"
                :controls="false"
                @change="handleChange"
              />
            </div>
          </div>
        </div>
         <hr>
        <div class="hover:bg-#fffcea">
          <!-- 日期 -->
          <span class="text-gray">
            2023/08/23 - 2023/12/31
          </span>
          <div>
            <span class="bg-amber-100 p-1">一</span>
            <span class="bg-amber-100 p-1">二</span>
            <span class="bg-amber-100 p-1">三</span>
          </div>
          <!--平假旺 -->
        <div class="flex flex-justify-between">
          <div class="flex flex-col flex-items-center">
            <span>平日</span>
            <div>
              2000
            </div>
          </div>
          <div class="flex flex-col flex-items-center">
            <span>假日</span>
            <div>
              3000
            </div>
          </div>
          <div class="flex flex-col flex-items-center">
            <span>旺日</span>
            <div>
              5000
            </div>
          </div>
        </div>
        </div>
      
      </div>
    </div>
  </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'

const num = ref(1)
const handleChange = (value) => {
  console.log(value)
}

const roomTypes = [
  '豪華雙人房',
  '豪華四人房',
  '溫馨家庭房',
  '海景雙床房'
]
</script>

<style scoped>
::v-deep() {
  .el-input-number {
    width: auto;
  }
}
</style>