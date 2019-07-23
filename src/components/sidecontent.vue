<template>
    <div class="profile">
        <div class="enlarge">
            <h2>Profile</h2>
            {{ profile }}
        </div>
        <div class="enlarge">
            <h2>Work experience</h2>
            <div v-for="workExperience in workExperiences" :key="`${workExperience.body}--workExperience`" class="ref-div">
                <h4>{{ workExperience.title }}</h4>
                <h4>{{ workExperience.position }}</h4>
                <h4>{{ workExperience.duration }}</h4>
                <h5>{{ workExperience.tools }}</h5>
                <p>{{ workExperience.body }}</p>
            </div>
            <h2>Education</h2>
            <div v-for="education in educations" :key="`${education.location}--education`" class="ref-div">
                <h4>{{ education.title }}</h4>
                <h5>{{ education.location }}</h5>
                <p>{{ education.duration }}</p>
            </div>
            <h2>Training course</h2>
            <div v-for="trainingCourse in trainingCourses" :key="`${trainingCourse.duration}--trainingCourse`" class="ref-div">
                <h4>{{ trainingCourse.title }}</h4>
                <h5>{{ trainingCourse.location }}</h5>
                <p>{{ trainingCourse.duration }}</p>
            </div>
            <h2>Languages</h2>
            <div v-for="languageSkills in languageSkills" :key="`${languageSkills.language}--languageSkills`" class="ref-div">
                <h4>{{ languageSkills.language }}</h4>
                <p>{{ languageSkills.proficiency }}</p>
            </div>
        </div>
    </div>  
</template>
<script>
export default {
    props: {
        profile: {
            type: String,
            required: true
        },
        workExperiences: {
            type: Array,
            default: () => []
        },
        educations: {
            type: Array,
            default: () => []
        },
        trainingCourses: {
            type: Array,
            default: () => []
        },
        languageSkills: {
            type: Array,
            default: () => []
        }
    }
    
}
</script>
<style src='../style.css'/>