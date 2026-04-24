<template>
  <div class="absolute inset-0 bg-black flex items-center justify-center overflow-hidden z-10 font-mono ">
    
    <div 
      class="relative w-full h-full flex items-center justify-center cursor-ns-resize"
      @wheel.prevent="handleWheel"
    >
      <img 
        :src="imagePath" 
        class="max-w-full max-h-full object-contain select-none"
      />
      
      <div class="absolute bottom-10 left-10 flex flex-col">
        <div class="w-8 h-[1px] bg-gray-600 mb-2"></div>
        <div class="border-l border-gray-600 pl-3">
          <div class="text-[10px] uppercase tracking-tighter text-gray-500 mb-1">
            {{ label }}
          </div>
          <div class="text-3xl font-extralight text-white tabular-nums">
            {{ String(currentIndex).padStart(2, '0') }}
            <span class="text-xs text-gray-600 ml-1">/ {{ maxIndex }}</span>
          </div>
        </div>
      </div>
    </div>

    <div class="absolute right-12 h-full flex items-center">
      <div class="relative w-1 h-48 flex justify-center bg-gray-800/30 rounded-full">
        <div class="absolute inset-y-4 w-[1px] bg-gray-700/50"></div>
        
        <input 
          type="range" 
          :min="0" 
          :max="maxIndex" 
          step="1"
          v-model.number="currentIndex" 
          class="compact-slider"
        />
      </div>
    </div>

  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// 定義 Props
const props = defineProps({
  // 資料夾路徑，例如 'CT_image' 或 'MRI_brain'
  folder: {
    type: String,
    required: true
  },
  // 檔案名稱前綴，例如 'test' 或 'img'
  prefix: {
    type: String,
    default: 'test'
  },
  // 總張數 (最大 Index)
  maxIndex: {
    type: Number,
    default: 31
  },
  // 檔案格式
  ext: {
    type: String,
    default: 'jpg'
  },
  // 左下角顯示的文字標籤
  label: {
    type: String,
    default: 'Depth Control'
  }
})

const currentIndex = ref(0)

// 計算最終圖片路徑
const imagePath = computed(() => {
  return `/${props.folder}/${props.prefix}${currentIndex.value}.${props.ext}`
})

const handleWheel = (event) => {
  if (event.deltaY > 0) {
    if (currentIndex.value < props.maxIndex) currentIndex.value++
  } else {
    if (currentIndex.value > 0) currentIndex.value--
  }
}
</script>

<style scoped>
/* 保持原本的 CSS 樣式不變 */
.compact-slider {
  -webkit-appearance: none;
  appearance: none;
  width: 12rem; 
  height: 100%;
  background: transparent;
  outline: none;
  transform: rotate(90deg);
  transform-origin: center;
  position: absolute;
  cursor: pointer;
  z-index: 20;
}
.compact-slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 4px;
  height: 16px;
  background: #ffffff;
  border-radius: 1px;
}
.compact-slider::-webkit-slider-thumb:hover {
  background: #10b981;
}
.cursor-ns-resize {
  cursor: ns-resize;
}
</style>