<!-- const scriptURL =
  "https://script.google.com/macros/s/AKfycbxkgWotCMyvIKoT9aGtPCndZdHtHrq8i972t9CKAVjO6xC7T0I/exec";
const form = document.forms["google-sheet"];

form.addEventListener("submit", (e) => {
  e.preventDefault();
  fetch(scriptURL, { method: "POST", body: new FormData(form) })
    .then((response) =>
      alert("Thanks for Contacting us..! We Will Contact You Soon...")
    )
    .catch((error) => console.error("Error!", error.message));
});


script code -------------------------
------------------------------------
var sheetName = 'Sheet1'
		var scriptProp = PropertiesService.getScriptProperties()

		function intialSetup () {
		  var activeSpreadsheet = SpreadsheetApp.getActiveSpreadsheet()
		  scriptProp.setProperty('key', activeSpreadsheet.getId())
		}

		function doPost (e) {
		  var lock = LockService.getScriptLock()
		  lock.tryLock(10000)

		  try {
			var doc = SpreadsheetApp.openById(scriptProp.getProperty('key'))
			var sheet = doc.getSheetByName(sheetName)

			var headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getValues()[0]
			var nextRow = sheet.getLastRow() + 1

			var newRow = headers.map(function(header) {
			  return header === 'timestamp' ? new Date() : e.parameter[header]
			})

			sheet.getRange(nextRow, 1, 1, newRow.length).setValues([newRow])

			return ContentService
			  .createTextOutput(JSON.stringify({ 'result': 'success', 'row': nextRow }))
			  .setMimeType(ContentService.MimeType.JSON)
		  }

		  catch (e) {
			return ContentService
			  .createTextOutput(JSON.stringify({ 'result': 'error', 'error': e }))
			  .setMimeType(ContentService.MimeType.JSON)
		  }

		  finally {
			lock.releaseLock()
		  }
		}

    function doGet(e){
  var x = HtmlService.createTemplateFromFile('display');
  var y = x.evaluate();
  var z = z.setXframeOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL);
  return z;
}

function getSheetData(){
  var a = SpreadsheetApp.getActiveSpreadsheet();
  var b = a.getSheetByName('');
  var c = b.getDataRange();
  return c.getValues(userData);
}


 -->
<!-- ------------------------------------------------------------ -->


<!-- <!DOCTYPE html>
<html lang="en">

<head>
  <base target="_top">
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Display Data</title>
</head>

<body>
  <center>
    <h1">
      All data from the survey
      </h1>

      <table style="border: 2px solid black;
    width: 500px;
    height: 500px;" cellpadding='5px'>
        <?var tableData = getSheetData();?>
        <?for(var i = 0; i< tableData.length; i++) { ?>
        <?if(i==0) { ?>
        <tr>
          <?for(var j = 0; j< tableData[i].length; j++){?>
          <th>
            <?= tableData[i][j] ?>
          </th>
          <? } ?>
        </tr>
        <? } else { ?>
        <tr>
          <?for(var j = 0; j< tableData[i].length; j++){?>
          <td>
            <?= tableData[i][j] ?>
          </td>
          <? } ?>
        </tr>
        <? } ?>
        <? } ?>
      </table>

  </center>
</body>

</html> -->
















<!-- 
//   const form = document.querySelector("form");
//         form.addEventListener("submit", (e) => {
//             e.preventDefault();
//             alert("Survey Submitted Successfully");
//             return window.location.replace("index.html");
//         });

Host id = AKfycbyuJFqtxRqKRNsOrsCLVWGVadZSnHgPtR1l4IqRlZdtYLnaH31tjK30G4_X-XBXT9MIVw  -->