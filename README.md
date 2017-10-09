# metafloor/bwip-js library modification for Angular2+.

## Installation

```
npm install bwip-angular2
```
After the installation of the library you must copy the folder "fonts" from 'node_modules/bwip-js/'
to the '<your_app_folder>/src/assets' and rename it (the folder "fonts") to "bwipjs-fonts"

## Usage

```javascript
import { Component } from '@angular/core';
import bwipjs from 'bwip-angular2';

@Component({
  selector: 'barcode',
  template: '<canvas id="barcodeCanvas"></canvas><div id="err"></div>',
  styleUrls: ['./barcode.component.css']
})
export class BarcodeComponent  {

  constructor() {
      bwipjs('barcodeCanvas', {
        bcid: 'datamatrix',       // Barcode type
        text: '123456789',   	  // Text to encode
        scale: 3,                 // 3x scaling factor
        height: 10,               // Bar height, in millimeters
        width: 10,
        includetext: true,        // Show human-readable text
        textxalign: 'center',      // Always good to set this
      }, function (err, cvs) {
        if (err) {
          document.getElementById('err').innerText = 'Error occured. See browser log for more information';
          console.log(err);
        } else {
        }
      });
   }
}
```
For more information and barcode options see 
[Barcode Writer in Pure PostScript](https://github.com/bwipp/postscriptbarcode). 
