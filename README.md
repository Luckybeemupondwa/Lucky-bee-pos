<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Lucky Bee POS</title>

<style>

body{
font-family:Arial;
margin:0;
background:#f2f2f2;
}

header{
background:#222;
color:white;
padding:15px;
text-align:center;
font-size:22px;
}

.container{
padding:15px;
}

.card{
background:white;
padding:15px;
margin-bottom:15px;
border-radius:8px;
box-shadow:0 2px 5px rgba(0,0,0,0.2);
}

button{
padding:10px;
margin:5px;
border:none;
background:#333;
color:white;
border-radius:6px;
font-size:14px;
}

button:hover{
background:#555;
}

input{
padding:8px;
margin:5px;
width:90%;
}

table{
width:100%;
border-collapse:collapse;
margin-top:10px;
}

table,th,td{
border:1px solid #ddd;
}

th,td{
padding:8px;
text-align:left;
}

footer{
background:#222;
color:white;
text-align:center;
padding:10px;
position:fixed;
bottom:0;
width:100%;
}

</style>
</head>

<body>

<header>
Lucky Bee POS System
</header>

<div class="container">

<div class="card">

<h3>Login</h3>

<input id="username" placeholder="Username"><br>
<input id="password" type="password" placeholder="Password"><br>

<button onclick="login()">Login</button>

</div>


<div class="card" id="dashboard" style="display:none">

<h3>Dashboard</h3>

<button onclick="showInventory()">Inventory</button>
<button onclick="showCheckout()">Checkout</button>
<button onclick="showSales()">Sales History</button>
<button onclick="logout()">Logout</button>

</div>


<div class="card" id="inventory" style="display:none">

<h3>Inventory</h3>

<input id="itemName" placeholder="Item name">
<input id="itemPrice" placeholder="Price">

<button onclick="addItem()">Add Item</button>

<table id="inventoryTable">
<tr>
<th>Item</th>
<th>Price</th>
</tr>
</table>

</div>


<div class="card" id="checkout" style="display:none">

<h3>Checkout</h3>

<p>Select item from inventory.</p>

</div>


<div class="card" id="sales" style="display:none">

<h3>Sales History</h3>

<p>No sales yet.</p>

</div>

</div>

<footer>
All Rights Reserved @ Lucky Bee
</footer>

<script>

function login(){

let u=document.getElementById("username").value
let p=document.getElementById("password").value

if(u==="admin" && p==="1234"){

document.getElementById("dashboard").style.display="block"

alert("Login successful")

}else{

alert("Wrong login")

}

}

function logout(){

location.reload()

}

function showInventory(){

hideAll()

document.getElementById("inventory").style.display="block"

}

function showCheckout(){

hideAll()

document.getElementById("checkout").style.display="block"

}

function showSales(){

hideAll()

document.getElementById("sales").style.display="block"

}

function hideAll(){

document.getElementById("inventory").style.display="none"
document.getElementById("checkout").style.display="none"
document.getElementById("sales").style.display="none"

}

function addItem(){

let name=document.getElementById("itemName").value
let price=document.getElementById("itemPrice").value

let table=document.getElementById("inventoryTable")

let row=table.insertRow()

row.insertCell(0).innerHTML=name
row.insertCell(1).innerHTML=price

}

</script>

</body>
</html>
