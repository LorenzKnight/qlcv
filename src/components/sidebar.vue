<template>
    <div class="profile">
        <div class="profile-pic" :style="{ background: `url(${profilePicture})`, backgroundPosition: 'center', backgroundSize: 'cover'}">
            
        </div> 
        <div class="profile-name">
            <h3>{{ name }}</h3>
        </div>
        <div class="contact-skills">
            <h2>Contact</h2>
            <div v-for="contact in contactInformation" :key="`${contact.name}--contact`" class="ref-div">
                <h4>{{ contact.name }}</h4>
                <p>{{ contact.phone }}</p>
                <p>{{ contact.email }}</p>
            </div>
        </div>
        <div class="contact-skills">
            <h2>Skills</h2>
            <ul>
                <li v-for="skill in skills">{{ skill }}</li><!-- (v-for) -->
            </ul>
        </div>  
    </div>
    
</template>
<!-- obs props {...} -->
<script>
export default {
    props: {
        contactInformation: {
            type: Array,
            default: () => []
        },
        skills: {
            type: Array
        },
        name: {
            type: String,
            required: true
        },
        profilePicture: {
            type: String,
            required: true
        }
    }
}
</script>
<style>

</style>