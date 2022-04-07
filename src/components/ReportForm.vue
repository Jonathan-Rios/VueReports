<template>
  <content>
    <h3>Período</h3>
    <div class="date-selector">
      <div class="form">
        <div>
          <label for="">Data inicial:</label>
          <input type="text">
        </div>
        <div>
          <label for="">Data final:</label>
          <input type="text">
        </div>
      </div>
      <ul>
        <li>Hoje</li>
        <li>Mês anterior</li>
        <li>Este Mês</li>
        <li>Últimos 6 meses</li>
      </ul>
    </div>
  </content>
</template>

<script>
  export default {
    name: 'ReportForm',
    props: {
      msg: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import '../global.css';

  content {
    display: flex;
    flex-direction: column;
    align-self: center;
    justify-content: center;
    width: 100%;
    padding: 20px 0;
  }

  content h3 {
    font-size: 20px;
    color: #828282;
    margin-bottom: 10px;  
  }

  .date-selector {
    border: 1px solid #C4C4C4;
    box-sizing: border-box;
    border-radius: 5px;
    display: flex;
    justify-content: space-between;
    padding: 20px;
    width: 80%;
  }

  .form {
    display: flex;
    align-self: center;
    justify-content: center;
  }
  .form div {
    margin: 10px;
    display: flex;
    flex-direction: column;
  }

  .form label {
    font-size: 12px;
    color: #999591;
  }

  .form input {
    border: 0;
    border-bottom: 1px solid #999591;
    color: #4F4F4F;
    max-width: 100px;
  }

  ul {
    list-style-type: none;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    margin-left: 30px;
  }

  li {
    display: inline-block;
    flex-basis: 35%;
    font-size: 12px;
    text-decoration-line: underline;
    color: #4F4F4F;
    cursor: pointer;
    white-space: nowrap;
  }

  li:hover {
    color: #C4C4C4; 
  }
</style>
