const functions = require('firebase-functions');
const express = require('express');


const displayqr = express();

	
displayqr.get('/displayqr', (request, response) => {
	console.log("response sent");
		response.send("testio/qrdisplay.html");
	});
	



 exports.displayqr = functions.https.onRequest(displayqr);
 
 exports.geturl = functions.https.onRequest((email) => {
 	console.log('logged in');
  
  console.log(email);
        var accounts = firebase.database().ref().child('accounts');
        accounts.orderByKey().on("value", function(snapshot) {
          snapshot.forEach(function(data) {
            if (data.child("Email").val() == email.val()) {
            console.log(data);
              var firstName = data.child("FirstName").val();
              var lastName = data.child("LastName").val();
   
             
              var url = ("http://qrickit.com/api/qr.php?d=" + firstName + " " + lastName + "     " + "August 14 6:15PM core workout class");
              console.log(url.val());
            return {
            	 "URL": url,};
              firebase.auth().signOut();
      }//end if statement
          });//end for each
        }); //end order by
 	});