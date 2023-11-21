<template>
<div>
   <ejs-button @click="exportImage">Export</ejs-button> 
<ejs-barcodegenerator id="barcode" width="200px" height="150px" value="SYNC123"
              type="Code39"   foreColor="blue" :displayText="displaytext"
></ejs-barcodegenerator> 
<ejs-qrcodegenerator width="200px" height="150px" value="SYNC123" foreColor="blue" :displayText="QRdisplaytext">
</ejs-qrcodegenerator>

<ejs-datamatrixgenerator width="200px" height="150px" value='SYNCUser' foreColor="blue" >
</ejs-datamatrixgenerator> 
</div>
</template>
<style>
   
</style>
<script>
import { BarcodeGeneratorComponent,QRCodeGeneratorComponent,DataMatrixGeneratorComponent } from '@syncfusion/ej2-vue-barcode-generator';
import {ButtonComponent} from '@syncfusion/ej2-vue-buttons';
export default {
    components: {
        'ejs-barcodegenerator': BarcodeGeneratorComponent,
        'ejs-qrcodegenerator' : QRCodeGeneratorComponent,
        'ejs-datamatrixgenerator' : DataMatrixGeneratorComponent,
        'ejs-button' :ButtonComponent
    },
  
    data () {
        return {
           
            displaytext: { text: 'CODE39-BARCODE' },
            QRdisplaytext: { text: 'Syncfusion'}
        }
    },
   methods: {
    exportImage: function() {
       
        let barcodeObj = document.getElementById("barcode");
        let barcodeInstance = barcodeObj.ej2_instances[0];
         
        barcodeInstance.exportImage('Syncfusion-image','JPG');
    }}
    
}
</script>
