<script setup>
const skills = [
  {
    name: 'Vue',
    desc: 'JavaScript Framework',
    svg: 'Vue.svg',
    color: 'rgba(65, 184, 131, 0.2)'
  },
  {
    name: 'JavaScript',
    desc: 'Programming Language',   
    svg: 'javascript.svg',
    color: 'rgba(247, 223, 30, 0.2)'
  },
  {
    name: 'HTML',
    desc: 'Markup Language',
    svg: 'html.svg',
    color: 'rgba(227, 76, 38, 0.2)'
  },
  {
    name: 'CSS',
    desc: 'Style Language',
    svg: 'css.svg',
    color: 'rgba(38, 77, 228, 0.2)'
  },
  {
    name: 'C++',
    desc: 'Programming Language',
    svg: 'c.svg',
    color: 'rgba(99, 109, 255, 0.2)'
  },
  {
    name: 'Git',
    desc: 'Version Control',
    svg: 'git.svg',
    color: 'rgba(240, 80, 51, 0.2)'
  },
  {
    name: 'GitHub',
    desc: 'Git Repository Host',
    svg: 'github.svg',
    color: 'rgba(36, 41, 46, 0.2)'
  },
  {
    name: 'C#',
    desc: 'Programming Language',
    svg: 'cs.svg',
    color: 'rgba(107, 70, 201, 0.2)'
  },
  {
    name: 'Figma',
    desc: 'Design Tool',
    svg: 'figma.svg',
    color: 'rgba(255, 64, 128, 0.2)'
  },
  {
    name: 'Unity',
    desc: 'Game Devlopment Engine',
    svg: 'unity.svg',
    color: 'rgba(0, 0, 0, 0.2)'
  },
  {
    name: 'PHP',
    desc: 'Web Backend',
    svg: 'php.svg',
    color: 'rgba(79, 93, 149, 0.2)'
  },
  {
    name: 'SQL Server',
    desc: 'Databases',
    svg: 'sql.svg',
    color: 'rgba(200, 50, 50, 0.2)'
  },
  {
    name: 'TailWind',
    desc: 'Css Framework',
    svg: 'tailwind.svg',
    color: 'rgba(56, 189, 248, 0.2)'
  },
  {
    name: 'Java',
    desc: 'Programming Language',
    svg: 'java.svg',
    color: 'rgba(176, 114, 25, 0.2)'
  },
  {
    name: 'Python',
    desc: 'Programming Language',
    svg: 'python.svg',
    color: 'rgba(53, 114, 165, 0.2)'
  },
  {
    name: 'TypeScript',
    desc: 'JavaScript but better',
    svg: 'typescript.svg',
    color: 'rgba(0, 122, 204, 0.2)'
  }
]

</script>


<template>
  <div class="skills-grid">
    <div class="skill-card" 
     v-for="skill in skills" 
     :key="skill.name"
     :style="{ backgroundColor: skill.color }">

      <div class="icon-area">
        <img :src="`/src/assets/svg/${skill.svg}`" :alt="skill.name" width="36" height="36" />
      </div>
      <div class="text-area">
        <div class="skill-header">{{ skill.name }}</div>
        <div class="skill-desc">{{ skill.desc }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  padding: 2rem;
  justify-items: center;
}

.skill-card {
  display: flex;
  align-items: center;
  border-radius: 16px;
  padding: 1.2rem 2rem;
  min-width: 260px;
  min-height: 90px;
  box-shadow: 0 2px 8px #0002;
  transition: box-shadow 0.2s, background-color 0.2s, filter 0.2s;
}

.skill-card:hover {
  box-shadow: 0 6px 24px #0006;
  filter: contrast(1.3)  ;
}


.icon-area {
  margin-right: 1.2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-area {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.skill-header {
  font-size: 1.2rem;
  font-weight: 600;
  color: #fff;
}

.skill-desc {
  font-size: 0.95rem;
  color: #b0b0b8;
  margin-top: 0.2rem;
  font-weight: 500;
}
.light-mode .skill-card{
    background-color: #e0e9f2;
} 
.light-mode .skill-header {
color:#19191b;
}
.light-mode .skill-desc {
color:#19191b;
}
</style>