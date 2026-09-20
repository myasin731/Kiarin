const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbzZWmoDlwpR866OPeRvK_hjDiCi7klS-0w271pTULCL1PnIc_5EW7FXpliwiK4xLE_w/exec";

// Contoh mengambil data dari Apps Script
fetch(SCRIPT_URL)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error("Error:", error));
