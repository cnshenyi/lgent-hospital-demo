<template>
  <div class="vertigo-projects">
    <!-- Header -->
    <div class="header">
      <div class="back-btn" @click="goBack">
        <svg viewBox="0 0 24 24" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M15 18l-6-6 6-6" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
      <h1 class="title">梅斯眩晕患者管理</h1>
      <div class="header-spacer"></div>
    </div>

    <!-- Project List -->
    <div class="project-list">
      <div class="project-card" v-for="project in projects" :key="project.id" @click="openProject(project)">
        <div class="project-icon">
          <svg viewBox="0 0 48 48" width="48" height="48" fill="none">
            <rect width="48" height="48" rx="8" fill="#1565C0"/>
            <rect x="14" y="12" width="20" height="24" rx="2" fill="white" opacity="0.9"/>
            <rect x="18" y="16" width="12" height="2" rx="1" fill="#1565C0" opacity="0.6"/>
            <rect x="18" y="20" width="8" height="1.5" rx="0.75" fill="#1565C0" opacity="0.4"/>
            <rect x="18" y="23.5" width="10" height="1.5" rx="0.75" fill="#1565C0" opacity="0.4"/>
          </svg>
        </div>
        <div class="project-info">
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-code">{{ project.code }}</p>
          <p class="project-date">{{ project.startDate }} - {{ project.endDate }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()

const projects = ref([
  {
    id: 1,
    title: '荜铃胃痛颗粒治疗功能性消化不良的有效性和安全性的真实世界研究',
    code: 'BLWT-001',
    startDate: '2023-06-29',
    endDate: '2024-11-30'
  },
  {
    id: 2,
    title: '心脏康复患者调研项目',
    code: 'EDC_EPRO',
    startDate: '-',
    endDate: '-'
  },
  {
    id: 3,
    title: '头晕登记管理系统',
    code: 'TYDJ',
    startDate: '-',
    endDate: '-'
  },
  {
    id: 4,
    title: '健力多®氨糖软骨素钙片真实世界回顾性研究',
    code: 'KEYLID2',
    startDate: '-',
    endDate: '-'
  },
  {
    id: 5,
    title: 'P16益生菌固体饮料辅助治疗慢性便秘患者的真实世界研究',
    code: 'P16-01',
    startDate: '-',
    endDate: '-'
  },
  {
    id: 6,
    title: 'EDC-cloud-TEST',
    code: 'EDC-cloud-TEST',
    startDate: '-',
    endDate: '-'
  }
])

const goBack = () => {
  router.back()
}

const openProject = (project) => {
  console.log('Open project:', project)
  // TODO: Navigate to project detail page
}
</script>

<style scoped>
.vertigo-projects {
  min-height: 100vh;
  background: #F5F5F5;
  padding-bottom: 20px;
}

/* Header */
.header {
  background: white;
  padding: 12px 16px;
  display: flex;
  align-items: center;
  box-shadow: 0 1px 4px rgba(0,0,0,0.08);
  position: sticky;
  top: 0;
  z-index: 10;
}

.back-btn {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  color: #333;
  transition: opacity 0.2s;
}

.back-btn:active {
  opacity: 0.6;
}

.title {
  flex: 1;
  text-align: center;
  font-size: 17px;
  font-weight: 600;
  color: #333;
  margin: 0;
}

.header-spacer {
  width: 40px;
}

/* Project List */
.project-list {
  padding: 12px 16px;
}

.project-card {
  background: white;
  border-radius: 12px;
  padding: 16px;
  margin-bottom: 12px;
  display: flex;
  gap: 12px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.06);
  cursor: pointer;
  transition: transform 0.15s, box-shadow 0.15s;
}

.project-card:active {
  transform: scale(0.98);
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.project-icon {
  flex-shrink: 0;
}

.project-info {
  flex: 1;
  min-width: 0;
}

.project-title {
  font-size: 15px;
  font-weight: 600;
  color: #333;
  margin: 0 0 8px 0;
  line-height: 1.4;
}

.project-code {
  font-size: 13px;
  color: #999;
  margin: 0 0 4px 0;
}

.project-date {
  font-size: 13px;
  color: #999;
  margin: 0;
}
</style>
