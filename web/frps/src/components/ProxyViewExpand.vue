<template>
  <el-form
    label-position="left"
    label-width="auto"
    inline
    class="proxy-table-expand"
  >
    <el-form-item label="名称">
      <span>{{ row.name }}</span>
    </el-form-item>
    <el-form-item label="类型">
      <span>{{ row.type }}</span>
    </el-form-item>
    <el-form-item label="加密">
      <span>{{ row.encryption }}</span>
    </el-form-item>
    <el-form-item label="压缩">
      <span>{{ row.compression }}</span>
    </el-form-item>
    <el-form-item label="上次启动">
      <span>{{ row.lastStartTime }}</span>
    </el-form-item>
    <el-form-item label="上次关闭">
      <span>{{ row.lastCloseTime }}</span>
    </el-form-item>

    <div v-if="proxyType === 'http' || proxyType === 'https'">
      <el-form-item label="域名">
        <span>{{ row.customDomains }}</span>
      </el-form-item>
      <el-form-item label="子域">
        <span>{{ row.subdomain }}</span>
      </el-form-item>
      <el-form-item label="位置">
        <span>{{ row.locations }}</span>
      </el-form-item>
      <el-form-item label="主机重写">
        <span>{{ row.hostHeaderRewrite }}</span>
      </el-form-item>
    </div>
    <div v-else-if="proxyType === 'tcpmux'">
      <el-form-item label="多路复用">
        <span>{{ row.multiplexer }}</span>
      </el-form-item>
      <el-form-item label="按 HTTP 用户路由">
        <span>{{ row.routeByHTTPUser }}</span>
      </el-form-item>
      <el-form-item label="域名">
        <span>{{ row.customDomains }}</span>
      </el-form-item>
      <el-form-item label="子域">
        <span>{{ row.subdomain }}</span>
      </el-form-item>
    </div>
    <div v-else>
      <el-form-item label="地址">
        <span>{{ row.addr }}</span>
      </el-form-item>
    </div>
  </el-form>

  <div v-if="row.annotations && row.annotations.size > 0">
  <el-divider />
  <el-text class="title-text" size="large">注解</el-text>
  <ul>
    <li v-for="item in annotationsArray()">
      <span class="annotation-key">{{ item.key }}</span>
      <span>{{  item.value }}</span>
    </li>
  </ul>
  </div>
</template>

<script setup lang="ts">

const props = defineProps<{
  row: any
  proxyType: string
}>()

// annotationsArray returns an array of key-value pairs from the annotations map.
const annotationsArray = (): Array<{ key: string; value: string }> => {
  const array: Array<{ key: string; value: any }> = [];
  if (props.row.annotations) {
    props.row.annotations.forEach((value: any, key: string) => {
      array.push({ key, value });
    });
  }
  return array;
}
</script>

<style>
ul {
  list-style-type: none;
  padding: 5px;
}

ul li {
  justify-content: space-between;
  padding: 5px;
}

ul .annotation-key {
  width: 300px;
  display: inline-block;
  vertical-align: middle;
}

.title-text {
  color: #99a9bf;
}
</style>
