<template>
  <el-form ref="postForm" :model="postForm">
    <sticky :class-name="'sub-navbar ' + postForm.status">
      <el-button v-if="!isEdit" @click="showGuide">显示帮助</el-button>
      <el-button v-loading="loading" @click="submitForm" type="success">{{isEdit ? '编辑电子书':'新增电子书'}}</el-button>
    </sticky>
    <div class="detail-container">
      <el-row>
        <Warning/>
        <el-col :span="24">
          <!-- 表单控件的具体样式 -->
        </el-col>
      </el-row>
    </div>
  </el-form>
</template>

<script>
import Sticky from '@/components/Sticky'
import Warning from './Warning'

export default {
  components: {
    Sticky,
    Warning
  },
  data() {
    return {
      loading: false,
      postForm: {
        status: 'draft'
      }
    }
  },
  props: {
    isEdit: Boolean
  },
  methods: {
    showGuide() {
      console.log('showGuide')
    },
    submitForm() {
      console.log('submitForm')
      this.loading = true
      setTimeout(() => {
        this.loading = false
      })
    }
  }
}
</script>

<style scoped>

</style>
