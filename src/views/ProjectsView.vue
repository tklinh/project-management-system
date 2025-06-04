<template>
  <a-form layout="inline">
    <a-form-item label="Tỉnh">
      <a-input
        placeholder="input placeholder"
      />
    </a-form-item>
    <a-form-item label="Trạng thái">
      <a-input
        placeholder="input placeholder"
      />
    </a-form-item>
    <a-form-item>
      <a-button type="primary">Tìm kiếm</a-button>
    </a-form-item>
  </a-form>
  <br />
  <BriefProjectInfo
    card-title="Khu đô thị mới Ninh Khánh"
    image-src="https://taybac.vn/uploads/up/taybac/project/2024/09/20/15/51/w1000/pv01726800666_905.jpg"
    :info="{
      location: 'Phường Nếnh, thị xã Việt Yên, tỉnh Bắc Giang',
      area: '9.86ha',
      status: 'Đang triển khai',
    }"
  />
  <br />
  <BriefProjectInfo
    card-title="Hưng Định City"
    image-src="https://taybac.vn/uploads/up/taybac/project/2020/11/25/15/39/w1000/cam1606271943_0054.jpg"
    :info="{
      location: 'Trần Phú, Bình Định, An Nhơn, Bình Định',
      area: '35ha',
      status: 'Đang triển khai',
    }"
  />
  <br />
  <BriefProjectInfo
    card-title="Mỹ Tho Riverside"
    image-src="https://taybac.vn/uploads/up/taybac/project/2020/11/25/19/33/w1000/2__1606285990_8713.jpg"
    :info="{
      location: 'Mỹ Tho, Tiền Giang',
      area: '7.3ha',
      status: 'Đang triển khai',
    }"
  />
</template>
<script setup lang="ts">
import BriefProjectInfo from "@/components/BriefProjectInfo.vue";
</script>
