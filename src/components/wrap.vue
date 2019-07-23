<template>
    <div v-if="!loading"><!--obs loading -->
      <!-- name -->
        <sidebar id="sidebar" 
        :name="cvData['en-US'].name"
        :contactInformation="cvData['en-US'].contactInformation"
        :skills="cvData['en-US']['skills']"
        :profilePicture="cvData['en-US'].profilePicture"
        />

        <sidecontent id="sidecontent"
        :profile="cvData['en-US'].profile"
        :work-experiences="cvData['en-US'].workExperience"
        :educations="cvData['en-US'].education"
        :training-courses="cvData['en-US'].trainingCourse"
        :language-skills="cvData['en-US'].languageSkills"
        />
    </div>
</template>

<script>
import sidebar from './sidebar.vue'
import sidecontent from './sidecontent.vue'
import axios from 'axios'

export default {
name: 'wrap',
  components: {
    sidebar,
    sidecontent
  },
    data() {
    return {
      cvData: {},
      loading: true
    }
  },
  mounted: function () {
    axios.get('https://queenslabcdn.blob.core.windows.net/resumes/tech/dawidParvulescu.json')
    .then((response) => {
      this.cvData = response.data
      this.loading = false
    })
  }
}
</script>
<style src="../style.css" />