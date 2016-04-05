var Spreadsheet = require('edit-google-spreadsheet');
var phantom = require('node-phantom');

function phantomGo(url){
    phantom.create(function(err,ph) {
      return ph.createPage(function(err,page) {
        return page.open(url,function(err,status) { //pass url & open
          console.log("opened site? ", status);
          console.log("for: " +url);
                
            setTimeout(function() { 
              return page.evaluate(function() {
                
              }, function(err,result) {
                
                ph.exit();
              });
            }, 1000);
         
        });
      });
    });

}

Spreadsheet.load({
    debug: true,
    spreadsheetName: '******',
    worksheetName: '******',

    oauth : {
        email: '********',
        keyFile: 'key.pem'
    }

}, function sheetReady(err, spreadsheet) {

    if (err) {
        throw err;
        console.log("sheetReady");
    }

    spreadsheet.receive(function(err, rows, info) {
        if (err) {
            console.log("tesT");
            throw err;
            console.log("sheetsheet");
        }
        
        //find # rows in obj -1 since first is header
        var numKeys = Object.keys(rows).length;
        var increment;
         //loop through all the rows 
        for (var i = 2; i <= numKeys; i++){
            var eachUrl = rows[i][2];
            //console.log('URL: '+eachUrl);
            
            var multi = 60000*i;
        //run each link after certain amt of time
        setTimeout(function(str1, str2,url) {
                console.log(str1);
                phantomGo(url);

            }, multi, multi, '', eachUrl); //, time between, str1, str2, url
            
        
        }
       
    });


});



