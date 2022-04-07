<template>
  <content class="main">
    <ReportForm class="ReportForm"/>
    <ReportTable class="ReportTable"/>
  </content>
</template>

<script>
import ReportForm from './components/ReportForm';
import ReportTable from './components/ReportTable';

export default {
  name: 'App',

  components: {
    ReportForm,
    ReportTable
  },
};
</script>

<style scoped>
  @import './global.css';

  .main {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .ReportForm {
    width: 1000px;
  }

  .ReportTable {
    width: 1000px;
  }
</style>