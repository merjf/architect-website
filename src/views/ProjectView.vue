<template>
  <div>
    <Header :page="'project'"/>
    <div class="section">
      <Project
        :detailed="true"
        :project="getCurrentProject()"
        class="project"
      />
    </div>
    <Footer />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import Project from '@/components/Project.vue';

@Component({
  components: {
    Header,
    Footer,
    Project,
  }
})
class ProjectView extends Vue {
  getCurrentProject(){
    return  {
      description: this.$route.params.description,
      title: this.$route.params.title,
      id: parseInt(this.$route.params.id),
      place: this.$route.params.place,
      mainFolder: this.$route.params.mainFolder,
      imageNumber: parseInt(this.$route.params.imageNumber)
    }
  }
}

export default ProjectView;
</script>

<style scoped lang="scss">

</style>