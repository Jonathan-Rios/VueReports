<template>
<table>
      <thead>
        <tr>
          <th v-for="item of columns" :key="item.label" 
          v-bind:class="item.class">{{ item.label}}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item of rows" :key="item.id">
          <td :class="columns[0].class">{{ item.name}}</td>
          <td :class="columns[1].class">{{ item.dailyValue | currency() }}</td>
          <td :class="columns[2].class">{{ item.occupiedPorts }}</td>
          <td :class="columns[3].class">{{ item.total | currency() }}</td>
        </tr>
        <tr>
          <td class="text-align-left">Maisinternet</td>
          <td>R$ 30,00</td>
          <td>450</td>
          <td>R$ 472.400,00</td>
        </tr>
        <tr>
          <td class="text-align-left">Mhnet</td>
          <td>R$ 30,00</td>
          <td>1.300</td>
          <td>R$ 1.365.000,00</td>
        </tr>
        <tr>
          <td class="text-align-left">Interconnect</td>
          <td>R$ 30,00</td>
          <td>200</td>
          <td>R$ 210.000,00</td>
        </tr>
        <tr>
          <td class="text-align-left">Maisinternet</td>
          <td>R$ 30,00</td>
          <td>300</td>
          <td>R$ 315.000,00</td>
        </tr>                        
      </tbody>  
      <tfoot>
        <tr>
          <td class="text-align-left total">Total</td>
          <td colspan="2"></td>
          <td>R$ 2.362.400,00</td>
        </tr>
      </tfoot>          
    </table>
</template>

<script>
  export default {
    name: 'ReportTable',
    filters: {
      currency(value){
        return new Intl.NumberFormat('pt-BR', 
        { style: 'currency',currency: 'BRL'})
        .format(value);
      }
    },
    data(){
      return {
        columns: [
          {
            label: 'Parceiros',
            field: 'name',
            type: 'text',
            class: 'text-align-left',
            filter: ''
          },
          {
            label: 'Valor diário da porta',
            field: 'dailyValue',
            type: 'currency',
            class: '',
            filter: 'currency()'
          },
          {
            label: 'Portas atualmente ocupadas',
            field: 'occupiedPorts',
            type: 'number',
            class: '',
            filter: ''
          },
          {
            label: 'Valor total',
            field: 'total',
            type: 'currency',
            class: '',
            filter: 'currency()'
          }
        ],
        rows: [
          { 
            id: 1,
            name: 'Maisinternet',
            dailyValue: 30, 
            occupiedPorts: 450,
            total: 472400
          },      
          {
            id: 2,
            name: 'Mhnet',
            dailyValue: 30, 
            occupiedPorts: 1300,
            total: 1365000
          },      
          {
            id: 3,
            name: 'Maisinternet',
            dailyValue: 30, 
            occupiedPorts: 200,
            total: 210000
          },      
          {
            id: 4,
            name: 'Maisinternet',
            dailyValue: 30, 
            occupiedPorts: 450,
            total: 315000
          }
        ],
        footer: [
          {
            label: 'Total',
            field: 'total',
            type: 'currency',
          }
        ]
      }
    }
}
</script>


<style scoped>
  @import '../global.css';
  
  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 14px;
    font-weight: regular;
    color: #312E38;

  }

  td, th {
    border-bottom: 2px solid #F4EDE8;
    padding: 8px;
    text-align: center;
  }

  td.left

  tr:nth-child(even){background-color: #f2f2f2;}

  tr:hover {background-color: #F4EDE8;}

  th {
    padding-top: 12px;
    padding-bottom: 12px;
    font-size: 16px;
    font-weight: bold;
    text-align: center;
    color: #999591;
  }

  tfoot{
    height: 50px;
    vertical-align: bottom;
  }

  td.total {
    font-size: 16px;
    font-weight: bold;
    color: #999591;
  }

  .text-align-left {
    text-align: left;
  }
</style>