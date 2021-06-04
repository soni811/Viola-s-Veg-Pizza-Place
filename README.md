# Viola-s-Veg-Pizza-Place
<!DOCTYPE html>
<html>
    <head>
        <title>Viola's Veg Pizza Place</title> 
  <style>
  
   input[type="number"],input[type="text"],input[type="tel"],textarea{
   width:98%;
   }
   select{
   width: 99%;
   }
   *{
   font-weight:bold;
   }
   
   
   body{
    background-color:#c8a869;
    background-repeat: no-repeat;
    background-size: 100%; 
    margin-top: 7%; 
    margin-bottom: 7%;   
   }    
      div{
    margin-left: auto;
    margin-right: auto;
    text-align: center;
   }
         h3{
      color: #FFFFFF;
      background-color: #7A000A;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
      width: 50%;
      padding: 5px;
      border-radius: 6px;
      }
         table,tr{
    width: 50%;
    margin-left: auto;
    margin-right: auto;
    background-color: #FFFFFF;
    border-radius: 6px;
      }
   
   td{
       border: solid 2px grey;
    color: #7A000A;
    text-align: left;
    border-spacing: 1px;
    border-radius: 6px;
   }
   
   #submit{
      color: #FFFFFF;
      background-color: #7A000A;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
      width: 50%;
      padding: 5px;
      border-radius: 6px;
     }

   #result{
    color: #FFFFFF;
    text-align: center;
    margin-right: auto;
    margin-left: auto;
    width: 50%;
   }

  </style>
 </head>
 
<body>
<script type="text/javascript">
function today() {
    today = new Date();
    var dd = today.getDate();
    var mm = today.getMonth()+1;
    var yyyy = today.getFullYear();
    if(dd<10) dd='0'+dd;
    if(mm<10) mm='0'+mm;
    document.getElementById("orderdate").value=yyyy+"-"+mm+"-"+dd;
}

function calculate() {
    var pizzatype = document.getElementById('pizzatype').value;
    var quantity = document.getElementById('quantity').value;
    var size = document.getElementById('size').value;
    var perpizzaCost=0;
    var totalpizzaCost;
    if(pizzatype=='Margherita') {
        if(size=='Regular') {
            perpizzaCost= 230;
        } else if(size=='Medium') {
            perpizzaCost= 320;
        } else {
            perpizzaCost=450;
        }
    } else {
        if(size=='Regular'){
            perpizzaCost= 380;
        } else if(size=='Medium') {
            perpizzaCost= 460;
        } else {
            perpizzaCost=620;
        }
    }
    totalpizzaCost=quantity*perpizzaCost;
    document.getElementById("result").innerHTML = "Your pizza order has been successfully placed and you need to pay Rs. "+totalpizzaCost;
return false;
}
   
   
    </script>
<div>
<h3>VIOLA'S VEG PIZZA PLACE</h3>
    <form onsubmit="return calculate()">
        <table>
         <tr>
                <td>Name</td>
                <td><input id="name" type="text" placeholder="Enter your name" pattern="[a-zA-Z ]+" required></td>
            </tr>
         <tr>
               <td>Phone Number</td>
            <td><input id="phonenumber" type="text" placeholder="Enter your phone number" required></td>
            </tr>
         
         <tr>
                <td>Address</td>
                <td><textarea id="address" rows="4" cols="50" required>Enter the address</textarea></td>
            </tr>
            
         <tr>
                <td>Order Date</td>
                <td><input id="orderdate" type="text" onfocus="today();" required></td>
            </tr>
            
         <tr>
          <td>Size</td>
          <td>
              <select id="size">
                  <option value="Regular">Regular</option>
                  <option value="Medium">Medium</option>
                  <option value="Large">Large</option>
              </select>
          </td>
         </tr>
         <tr>
          <td>Pizza Type</td>
          <td>
              <select id="pizzatype">
                  <option value="Margherita">Margherita</option>
                  <option value="Cheese n Corn">Cheese n Corn</option>
              </select>
          </td>
         </tr>
         
         <tr>
                <td>Quantity</td>
                <td><input id="quantity" type="text" required></td>
</tr> 
        </table>
        
        <p><input type="submit" id="submit" name="submit" value="CONFIRM ORDER"/></p>
        <div id="result"></div>
    </form>
</div>
</body>
</html>
