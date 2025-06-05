<template>
  <div class="timeline-container">
    <div class="timeline-line"></div>
    <div class="timeline-fade"></div>
    <div
      v-for="(entry, index) in timeline"
      :key="index"
      class="timeline-entry"
      :class="{
        'left': index % 2 === 0,
        'right': index % 2 !== 0
      }"
    >
      <div class="timeline-content">
        <div class="timeline-year">
          <h2>{{ entry.year }} <span>{{ entry.duration }}</span></h2>
        </div>
        <h3 class="timeline-title">{{ entry.title }}</h3>
        <p class="industry">{{ entry.industry }} • {{ entry.location }}</p>
        <p class="description">{{ entry.description }}</p>
        <ul>
          <li v-for="(point, i) in entry.points" :key="i">{{ point }}</li>
        </ul>
        <div class="tags">
          <span v-for="(tag, j) in entry.tags" :key="j" class="tag">{{ tag }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const timeline = ref([
  {
    year: '2023',
    duration: '1 year',
    title: 'Junior Full Stack Developer',
    industry: 'Automotive Industry',
    location: 'Germany',
    description: 'Currently in vocational training while developing digital tools and applications for the automotive industry.',
    points: [
      'Leading development team of 3 engineers',
      'Developed simulation software for industrial screw controllers',
      'Implemented AI-driven solutions for management systems'
    ],
    tags: ['C#', 'Python', 'TensorFlow']
  },
  {
    year: '2017',
    duration: '6 years',
    title: 'Student',
    industry: 'Realschule',
    location: 'Germany',
    description: 'Completed school education with focus on technical subjects.',
    points: [
      'Specialised in technical and IT courses',
      "Participated in Harvard’s CS50x online computer science program",
      'Developed strong interest in cybersecurity',
      'Active participant in HackTheBox challenges',
      'Completed with strong academic performance'
    ],
    tags: ['Math', 'Physics', 'Chemistry', 'IT']
  },
  {
    year: '2013',
    duration: '4 years',
    title: 'Student',
    industry: 'Grundschule',
    location: 'Germany',
    description: 'Started my educational journey with early exposure to technology',
    points: [
      'First introduction to computers and technology',
      'Developed early interest in programming',
      'Built foundation for future technical education'
    ],
    tags: ['Math', 'Basic Computing', 'Problem Solving']
  }
]);
</script>

<style scoped>
.timeline-container {
  position: relative;
  background-color: #0d0d0d;
  padding: 6rem 2rem;
  color: #fff;
  font-family: 'Segoe UI', sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}

.timeline-line {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 50%;
  width: 2px;
  background: linear-gradient(to bottom, #ff0080, #7928ca);
  box-shadow: 0 0 20px rgba(255, 0, 128, 0.7);
  transform: translateX(-50%);
  z-index: 0;
}

.timeline-fade {
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 100%;
  height: 80px;
  background: linear-gradient(to bottom, rgba(13,13,13,0) 0%, #0d0d0d 100%);
  transform: translateX(-50%);
  z-index: 1;
}

.timeline-entry {
  position: relative;
  width: 100%;
  max-width: 1000px;
  display: flex;
  justify-content: flex-start;
  padding: 2rem 0;
  z-index: 2;
}

.timeline-entry.left {
  justify-content: flex-end;
}

.timeline-entry.right {
  justify-content: flex-start;
}

.timeline-content {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(6px);
  padding: 1.75rem;
  border-radius: 1rem;
  border: 1px solid rgba(255, 255, 255, 0.08);
  box-shadow: 0 0 20px rgba(255, 0, 128, 0.2);
  max-width: 460px;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.timeline-content:hover {
  transform: translateY(-4px);
  box-shadow: 0 0 30px rgba(255, 94, 0, 0.6);
}

.timeline-year h2 {
  font-size: 2rem;
  font-weight: 700;
  color: #00ffff;
  text-shadow: 0 0 20px #00ffff;
  margin: 0;
}

.timeline-year span {
  font-size: 0.875rem;
  color: #aaa;
  margin-left: 0.25rem;
}

.timeline-title {
  font-size: 1.3rem;
  margin: 0.75rem 0 0.3rem;
  position: relative;
  display: inline-block;
  transition: color 0.3s ease;
}

.timeline-title::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  left: 0;
  bottom: -4px;
  background: #ff6a00;
  transition: width 0.3s ease;
}

.timeline-content:hover .timeline-title {
  color: #ff6a00;
}

.timeline-content:hover .timeline-title::after {
  width: 100%;
}

.industry {
  color: #aaa;
  font-size: 0.85rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
}

.description {
  font-style: italic;
  margin-bottom: 0.5rem;
  color: #ddd;
}

ul {
  list-style-type: '→ ';
  padding-left: 1.5rem;
  margin-bottom: 0.75rem;
  color: #ccc;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  background: linear-gradient(to right, #7928ca, #ff0080);
  padding: 0.35rem 0.75rem;
  border-radius: 999px;
  font-size: 0.75rem;
  color: white;
  box-shadow: 0 0 10px rgba(255, 0, 128, 0.4);
}

@media screen and (max-width: 768px) {
  .timeline-entry {
    justify-content: center !important;
    text-align: center;
  }

  .timeline-entry.left,
  .timeline-entry.right {
    justify-content: center !important;
  }

  .timeline-content {
    margin-top: 2rem;
  }
}
</style>
