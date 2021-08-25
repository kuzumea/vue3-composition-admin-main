<template>
  <div class="container">
    <el-row>
      <el-col>
        <el-input
          style="width: 300px;"
          v-model="input"
          placeholder="请输入内容"
        />
        <el-select
          v-model="value"
          placeholder="请选择"
          clearble
        >
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
          />
        </el-select>

        <el-button type="primary">
          搜索
        </el-button>
        <el-radio
          v-model="radio"
          label="1"
        >
          备选项
        </el-radio>
      </el-col>
    </el-row>
  </div>
</template>
<script lang="ts">
import { defineComponent, toRefs, reactive } from 'vue'

export default defineComponent({
  setup() {
    const dataMap = reactive({
      input: '',
      value: '',
      options: [
        {
          value: '选项1',
          label: '黄金糕'
        },
        {
          value: '选项2',
          label: '双皮奶'
        },
        {
          value: '选项3',
          label: '蚵仔煎'
        },
        {
          value: '选项4',
          label: '龙须面'
        },
        {
          value: '选项5',
          label: '北京烤鸭'
        }
      ],
      radio: '1'
    })
    return { ...toRefs(dataMap) }
  }
})
</script>
