<!DOCTYPE html>

<html lang="bn"> <head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1" name="viewport"/>
<title>উদ্যান অনলাইন স্টোর</title>
<style>   

.product-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  justify-items: center;
}

.product-grid .product {
  background: #ffffff;
  padding: 6px;
  border-radius: 6px;
  box-shadow: 0 0 4px rgba(0,0,0,0.1);
  font-size: 13px;
  text-align: center;
  max-width: 120px;
  min-height: 120px;
  overflow: hidden;
}

.product-grid img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  margin-bottom: 5px;
}

.product-grid h3, 
.product-grid p {
  margin: 4px 0;
  line-height: 1.2;
}

  
  
  
  
.chat-message {
  margin: 5px 0;
  padding: 8px 12px;
  border-radius: 12px;
  max-width: 70%;
  clear: both;
}
.admin-msg {
  background-color: #d1e7dd;
  float: right;
  text-align: right;
}
.user-msg {
  background-color: #f8d7da;
  float: left;
  text-align: left;
}
.sender-name {
  font-weight: bold;
  font-size: 12px;
  margin-bottom: 2px;
  display: block;
}
.chat-message {
  margin: 5px 0;
  padding: 8px 12px;
  border-radius: 12px;
  max-width: 70%;
  clear: both;
}
.admin-msg {
  background-color: #d1e7dd;
  float: right;
  text-align: right;
}
.user-msg {
  background-color: #f8d7da;
  float: left;
  text-align: left;
}
.sender-name {
  font-weight: bold;
  font-size: 12px;
  margin-bottom: 2px;
  display: block;
}
    body {    
      font-family: 'SolaimanLipi', Arial, sans-serif;    
      background:#4CACAF;    
      color:green;    
      margin: 0;    
      padding: 0;    
    }  header{  
background:#4CAF50;  
color: white;  
font-size: 14;
padding:10px;  
text-align:center ;  
}  
.user-info {  
background: #e0f7e0;  
padding: 10px;  
font-size: 14px;  
text-align: center;  
}  
.container {  
padding: 20px;  
max-width: 600px;  
margin: auto;  
}  
input[type="text"], input[type="number"], input[type="password"], select {  
width: 100%;  
padding: 10px;  
margin-bottom: 10px;  
font-size: 16px;  
box-sizing: border-box;  
}  
button {  
padding: 8px 12px;  
margin: 5px 2px 5px 0;  
background: #4CAF50;  
border: none;  
color: white;  
border-radius: 4px;  
cursor: pointer;  
font-size: 14px;  
}  
button:disabled {  
background: gray;  
cursor: not-allowed;  
}
  .dashboardProductList {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* ২ কলাম */
    gap: 10px; /* আইটেমের মাঝে ফাঁকা */
    padding-left: 0;
    list-style-type: block;
  }
.dashboardProductList li {
    background: #ffffff;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0 0 5px rgba(0,0,0,0.1);
  }
#adminPanel {  
background: #fff8e1;  
padding: 15px;  
margin-top: 30px;  
border: 1px solid #ccc;  
border-radius: 8px;  
}  
footer {  
text-align: center;  
background: #ddd;  
padding: 10px;  
font-size: 13px;  
margin-top: 40px;  
}  
#changePasswordBox {  
background: #ffffcc;  
padding: 10px;  
margin-top: 20px;  
display: none;  
border-radius: 6px;  
}  /* Floating Cart Styles */
#floatingCartIcon {
position: fixed;
top: 120px;
right: 20px;
background: #FFFFFF;
color: white;
border-radius: 50%;
width: 50px;
height: 50px;
font-size: 24px;
text-align: center;
line-height: 50px;
cursor: pointer;
z-index: 9999;
box-shadow: 0 0 10px #999;
user-select: none;
}

#floatingCartBox {
position: fixed;
top: 80px;
right: 20px;
background: white;
border: 1px solid #ccc;
border-radius: 8px;
width: 320px;
max-height: 400px;
padding: 15px;
box-shadow: 0 0 15px rgba(0,0,0,0.2);
display: none;
z-index: 9998;
overflow-y: auto;
font-size: 14px;
}

#floatingCartBox h4 {
margin-top: 0;
margin-bottom: 10px;
}

.cart-item {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 8px;
}
.cart-item > div {
display: flex;
align-items: center;
gap: 6px;
}
.cart-item button {
font-size: 14px;
padding: 3px 6px;
cursor: pointer;
background:#FFFFFF;
border: none;
border-radius: 4px;
color: green;
user-select: none;
}
.cart-item button:disabled {
background: gray;
cursor: not-allowed;
}

  </style>
</head>
<body> <header>
<h1> স্বাগতম </h1>
<h2> 🌿 উদ্যান অনলাইন স্টোর</h2>
</header>
<div class="user-info" id="userInfoBox" style="display:none;">
<p><strong>👤 <span id="userNameDisplay"></span></strong> | 📱 <span id="userMobileDisplay"></span></p>
<button onclick="logout()">🚪 লগআউট</button>
<!-- মাই একাউন্ট বাটন -->
<button onclick="showMyAccount()">📂 মাই একাউন্ট</button>
<!-- মাই অর্ডার বাটন -->
<button id="myOrdersBtn" onclick="showMyOrders()">📦 মাই অর্ডার</button>
<!-- মাই একাউন্ট বক্স -->
<div id="myAccountBox" style="display:none; background:#e0f7e0; padding:10px; margin-top:10px; border-radius:6px;">
<h3>📂 মাই একাউন্ট</h3>
<p><strong>নাম:</strong> <input id="editName" type="text"/></p>
<p><strong>মোবাইল:</strong> <input id="editMobile" type="text"/></p>
<p><strong>ঠিকানা:</strong> <input id="editAddress" type="text"/></p>
<p><strong>পাসওয়ার্ড:</strong> <input id="editPassword" type="password"/></p>
<button onclick="saveProfile()">✅ সংরক্ষণ করুন</button>
</div>
<!-- ইউজার হিস্টোরি দেখার বাটন (শুরুতে লুকানো থাকবে) -->
<button id="userHistoryBtn" onclick="toggleUserBox()" style="display:none; margin-top:10px;">
  👥 ইউজার দেখুন
</button>
<!-- ইউজার তালিকা দেখানোর বক্স (টগল হবে) -->
<div id="userBox" style="display:none; background:#eef; padding:10px; margin-top:10px; border-radius:8px;">
<h3>👥 ইউজার তালিকা</h3>
<ul id="adminUserList" style="list-style:none; padding:0;"></ul>
</div>
<button id="adminBtn" onclick="toggleAdmin()" style="display:none;">🔐 অ্যাডমিন প্যানেল</button>
</div> <div class="container" id="authBox">
<h2>🔐 লগইন করুন / নিবন্ধন করুন</h2> <div id="loginForm">
<input id="loginMobile" placeholder="মোবাইল নম্বর" type="text"/>
<input id="loginPass" placeholder="পাসওয়ার্ড" type="password"/>
<button onclick="login()">লগইন</button>
<p>নতুন? <a href="#" onclick="showRegister()">রেজিস্ট্রেশন করুন</a></p>
</div> <div id="registerForm" style="display:none;">
<input id="regName" placeholder="নাম" type="text"/>
<input id="regMobile" placeholder="মোবাইল নম্বর" type="text"/>
<input id="regAddress" placeholder="ঠিকানা" type="text"/>
<input id="regPass" placeholder="পাসওয়ার্ড" type="password"/>
<select id="regRole">
<option value="user">সাধারণ ইউজার</option>
<option value="admin">অ্যাডমিন</option>
</select>
<button onclick="register()">রেজিস্টার</button>
<p>ইতিমধ্যে সদস্য? <a href="#" onclick="showLogin()">লগইন করুন</a></p>
</div>
</div> <div class="container" id="storeBox" style="display:none;">
<div id="searchFilterBox">
<input id="searchBox" placeholder="🔍 পণ্য সার্চ করুন..." type="text"/>
<select id="categoryFilter" onchange="filterByCategory()" style="margin-bottom: 10px; padding: 8px; font-size: 16px;">
<option value="">-- ক্যাটাগরি নির্বাচন করুন --</option>
<option value="খাদ্য">🍚 খাদ্য</option>
<option value="বস্ত্র">👕 বস্ত্র</option>
<option value="বাসস্থান">🏠 বাসস্থান</option>
<option value="শিক্ষা">📚 শিক্ষা</option>
<option value="চিকিৎসা">💊 চিকিৎসা</option>
<option value="লেনদেন">💸 লেনদেন</option>
<option value="যাতায়াত">🚌 যাতায়াত</option>
<option value="প্রয়জনীয় জিনিস">🛍️ প্রয়োজনীয়</option>
<option value="হার্ডওয়্যার">🔧 হার্ডওয়্যার</option>
<option value="ইলেকট্রনিকস">📺 ইলেকট্রনিকস</option>
</select>
</div>
<div class="product-grid" id="productList"></div>
<form id="orderForm" onsubmit="submitOrder(event)" style="display:none;">
<p>👇 নিচের বাটন চাপলেই অর্ডার কনফার্ম হবে:</p>
<button type="submit">✅ অর্ডার কনফার্ম</button>
</form>
<div id="adminPanel" style="display:none;">
<label for="statusFilter">📊 অর্ডার স্ট্যাটাস ফিল্টার করুন: </label><select id="statusFilter" onchange="filterOrdersByStatus()" style="margin:10px; padding:6px;"><option value="">-- সব --</option><option value="pending">⏳ Pending</option><option value="received">✅ Received</option><option value="sent">🚚 Sent</option><option value="delivered">📦 Delivered</option></select><h2>🛠️ পণ্য ব্যবস্থাপনা</h2>
<button onclick="viewAllOrders()">📄 সব অর্ডার দেখুন</button>
<button onclick="printAllOrders()">🖨️ সব অর্ডার প্রিন্ট করুন</button>
<div id="allOrdersBox" style="display:none; margin-top:15px; background:#ffffe0; padding:10px; border-radius:8px;">
<h3>📋 সকল অর্ডার তালিকা</h3>
<ul id="allOrderList"></ul>
</div> <input id="adminName" placeholder="পণ্যের নাম" type="text"/>
<input id="adminPrice" placeholder="দাম" type="number"/>
<input accept="image/*" id="productImage" type="file"/><br/>
<input id="adminStock" placeholder="স্টক" type="number"/>
<select id="adminCategory" style="margin-bottom:10px;">
<option value="">-- ক্যাটাগরি নির্বাচন করুন --</option>
<option value="খাদ্য">🍚 খাদ্য</option>
<option value="বস্ত্র">👕 বস্ত্র</option>
<option value="বাসস্থান">🏠 বাসস্থান</option>
<option value="শিক্ষা">📚 শিক্ষা</option>
<option value="চিকিৎসা">💊 চিকিৎসা</option>
<option value="লেনদেন">💸 লেনদেন</option>
<option value="যাতায়াত">🚌 যাতায়াত</option>
<option value="প্রয়জনীয় জিনিস">🛍️ প্রয়োজনীয়</option>
<option value="হার্ডওয়্যার">🔧 হার্ডওয়্যার</option>
<option value="ইলেকট্রনিকস">📺 ইলেকট্রনিকস</option>
</select>
<button onclick="addNewProduct()">➕ পণ্য যোগ করুন</button>
<h3>📦 বিদ্যমান পণ্য</h3>
<ul id="adminProductList"></ul>
<div id="changePasswordBox">
<h3>পাসওয়ার্ড পরিবর্তন</h3>
<input id="oldPass" placeholder="পুরানো পাসওয়ার্ড" type="password">
<input id="newPass" placeholder="নতুন পাসওয়ার্ড" type="password"/>
<button onclick="changePassword()">পরিবর্তন করুন</button>
</input></div>
<!-- ইউজার তালিকা দেখানোর জন্য সেকশন -->
<div id="adminUserListContainer" style="display:none; margin-top:20px;">
<h3>👥 ইউজার তালিকা</h3>
<ul id="adminUserList" style="list-style-type:none; padding:0;"></ul>
</div>
</div> <footer>    
  © 2025 উদ্যান | তৈরি করেছেন রিদওয়ান হাসান    
  <div id="adminDashboard" style="display:none; background:#e0f7fa; padding:15px; margin-bottom:20px; border-radius:8px;">
<h2>🛠️ অ্যাডমিন ড্যাশবোর্ড</h2>
<p>মোট ইউজার: <strong><span id="totalUsers">0</span></strong></p>
<p>মোট অর্ডার: <strong><span id="totalOrders">0</span></strong></p>
<h3>পণ্যসমূহ</h3>
<ul id="dashboardProductList">
<li>প্রোডাক্ট ১</li>
<li>প্রোডাক্ট ২</li>
<li>প্রোডাক্ট ৩</li>
<li>প্রোডাক্ট ৪</li>
</ul>
<div id="salesSummary" style="margin-top:20px;"><h3>📈 মাসভিত্তিক বিক্রির সারসংক্ষেপ</h3><div id="salesChart">⏳ লোড হচ্ছে...</div></div></div>
<!-- HTML: ফ্লোটিং চ্যাট বাটন এবং চ্যাট উইন্ডো -->
<div id="chatButton" onclick="openChat()" style="
  position: fixed; bottom: 20px; right: 20px;
  background: #4CAF50; color: white;
  border-radius: 50%; width: 60px; height: 60px;
  font-size: 30px; line-height: 60px;
  text-align: center; cursor: pointer; z-index: 10000;
  user-select: none;">💬</div>
<div id="chatWindow" style="
  display: none;
  position: fixed; top: 0; left: 0; right: 0; bottom: 0;
  background: white;
  z-index: 10001;
  padding: 10px;
  box-sizing: border-box;
  flex-direction: column;
  max-width: 400px;
  margin: auto;
  border: 1px solid #4CAF50;
  border-radius: 8px;
  box-shadow: 0 0 15px rgba(0,0,0,0.3);
  ">
<div id="userList" style="margin-bottom:10px;"></div>
<div style="display:flex; justify-content: space-between; align-items: center;">
<h3 style="margin: 0; color: #4CAF50;">চ্যাট করুন</h3>
<button onclick="closeChat()" style="font-size:18px; cursor:pointer;">✖</button>
</div>
<!-- এডমিন হলে ইউজার তালিকা দেখাবে -->
<div id="userListBox" style="display: none; margin-bottom: 10px; border:1px solid #ddd; padding:5px; max-height: 150px; overflow-y:auto;">
<strong>ইউজার তালিকা:</strong>
<div id="userList"></div>
</div>
<div id="chatMessages" style="
    height: 60vh;
    overflow-y: auto;
    border: 1px solid #ddd;
    padding: 10px;
    margin: 10px 0;
    font-size: 14px;
    background: #f9f9f9;
  "></div>
<form id="chatForm" onsubmit="sendChatMessage(event)" style="display:flex; gap: 5px;">
<input autocomplete="off" id="chatInput" placeholder="আপনার মেসেজ লিখুন..." style="flex-grow:1; padding: 8px; font-size:14px;" type="text"/>
<button style="background:#4CAF50; color:#fff; border:none; padding: 8px 12px; cursor:pointer;" type="submit">পাঠান</button>
</form>
</div>
<div id="floatingCartIcon" onclick="toggleFloatingCart()">🛒</div>
</footer> <!-- Floating Cart Details --> <div id="floatingCartBox">
<h4>🛍️ আপনার কার্ট</h4>
<div id="floatingCartItems">কার্ট খালি</div>
<p><strong>মোট: ৳<span id="floatingCartTotal">0</span></strong></p>
<button onclick="clearCart()" style="margin-top:10px;">🧹 কার্ট খালি করুন</button></div> <script>    








// ইউজার তালিকা টগল করার ফাংশন
function toggleUserBox() {
  const box = document.getElementById("userBox");
  if (box.style.display === "none" || box.style.display === "") {
    box.style.display = "block";
    renderAdminUserList();
  } else {
    box.style.display = "none";
  }
}

// ইউজার তালিকা রেন্ডার ফাংশন
function renderAdminUserList() {
  const list = document.getElementById("adminUserList");
  list.innerHTML = "";

  // লোকালস্টোরেজ থেকে ইউজার লিস্ট নিয়ে আসো
  const users = JSON.parse(localStorage.getItem("users")) || [];

  if (users.length === 0) {
    list.innerHTML = "<li>❌ কোনো ইউজার পাওয়া যায়নি।</li>";
    return;
  }

  users.forEach((user, index) => {
    const li = document.createElement("li");
    li.style.marginBottom = "10px";
    li.style.padding = "8px";
    li.style.border = "1px solid #ccc";
    li.style.borderRadius = "6px";
    li.style.background = user.role === "admin" ? "#e8f5e9" : "#fff";

    li.innerHTML = `
      <strong>${user.name}</strong> (${user.role})<br>
      মোবাইল: ${user.mobile}<br>
      পাসওয়ার্ড: ${user.pass || "নাই"}<br>
      ঠিকানা: ${user.address || "নাই"}<br>
      <button onclick="deleteUser(${index})" style="margin-top:5px; background:#e53935; color:white; border:none; padding:4px 8px; border-radius:4px; cursor:pointer;">🗑️ মুছুন</button>
    `;

    list.appendChild(li);
  });
}

// ইউজার মুছার ফাংশন
function deleteUser(index) {
  let users = JSON.parse(localStorage.getItem("users")) || [];
  users.splice(index, 1);
  localStorage.setItem("users", JSON.stringify(users));
  renderAdminUserList(); // রিফ্রেশ করো তালিকা
}







function updateOrderStatus(index, status) {
  console.log("✅ বাটনে ক্লিক হয়েছে:", index, status);
  alert(`✅ বাটনে ক্লিক হয়েছে:\nঅর্ডার নম্বর: ${index}\nনতুন অবস্থা: ${status}`);

  if (!orders[index]) {
    alert("❌ অর্ডার পাওয়া যায়নি!");
    return;
  }

  if (status === "cancelled") {
    // ❌ বাতিল হলে অর্ডার লিস্ট থেকে ডিলিট করো
    orders.splice(index, 1);
  } else {
    // অন্যথায় শুধু স্ট্যাটাস আপডেট করো
    orders[index].status = status;
  }

  localStorage.setItem("orders", JSON.stringify(orders));
  viewAllOrders();
}

function filterByCategory() {
  const selected = document.getElementById("categoryFilter").value;
  displayProducts("", selected);
}


function updateProductPrice(id, newPrice) {
  const product = products.find(p => p.id === id);
  if (!product) return;
  product.price = parseInt(newPrice);
  saveProducts();
  renderAdminList(); // বিদ্যমান তালিকাও রিফ্রেশ হবে
}

function updateProductStock(id, newStock) {
  const product = products.find(p => p.id === id);
  if (!product) return;
  product.stock = parseInt(newStock);
  saveProducts();
  renderAdminList();
}

function displayProducts(filter = "", category = "") {
  const list = document.getElementById("productList");
  list.innerHTML = "";

  const filtered = products.filter(p =>
    p.name.toLowerCase().includes(filter.toLowerCase()) &&
    (category === "" || p.category === category)
  );





  const user = JSON.parse(localStorage.getItem("loggedInUser"));

  // ✅ যদি ইউজার না থাকে বা রোল ইউজার না হয়, তাহলে কিছুই দেখাবেনা
  if (!user || user.role !== "user") return;

  filtered.forEach(product => {
    const item = document.createElement("div");
    item.className = "product";

    const imageHTML = product.image ? `<img src="${product.image}" width="120" alt="ছবি"><br>` : "";

    item.innerHTML = `
      ${imageHTML}
      <h3>${product.name}</h3>
      <p>দাম: ৳${product.price}</p>
      <p>স্টক: ${product.stock}</p>
      <button onclick="addToCart(${product.id})" ${product.stock <= 0 ? "disabled" : ""}>🛒 কার্টে যোগ</button>
    `;

    list.appendChild(item);
  });

  controlFloatingCartVisibility();
}





function viewAllOrders() {
  const list = document.getElementById("allOrderList");
  const box = document.getElementById("allOrdersBox");

  box.style.display = box.style.display === "none" ? "block" : "none";

  if (orders.length === 0) {
    list.innerHTML = "<li>❌ কোনো অর্ডার পাওয়া যায়নি।</li>";
    return;
  }

  list.innerHTML = "";
 orders.slice().reverse().forEach((order, index) => {
  const actualIndex = orders.length - 1 - index;
    const li = document.createElement("li");
    let items = order.items.map(i => `${i.name} (${i.qty}x)`).join(", ");
    let total = order.items.reduce((t, i) => t + (i.total || 0), 0);

    li.innerHTML = `
      🕒 ${order.date} | 👤 ${order.name} (${order.userMobile})<br>
      🛍️ ${items} | 💰 মোট: ৳${total}<br>
      🔄 অবস্থা: <strong>${order.status || "pending"}</strong><br>
  <button onclick="updateOrderStatus(${actualIndex}, 'received')">✅ গ্রহণ</button>
  <button onclick="updateOrderStatus(${actualIndex}, 'cancelled')">❌ বাতিল</button>
  <button onclick="updateOrderStatus(${actualIndex}, 'sent')">🚚 পাঠানো</button>
  <button onclick="updateOrderStatus(${actualIndex}, 'delivered')">📦 ডেলিভারি</button>
<button onclick="printSingleOrder(${actualIndex})">🖨️ প্রিন্ট</button>
    `;
    li.style.marginBottom = "15px";
    li.style.padding = "10px";
    li.style.background = "#000000";
    li.style.borderRadius = "6px";
    list.appendChild(li);
  });
}
function controlFloatingCartVisibility() {
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  const cartIcon = document.getElementById("floatingCartIcon");
  const cartBox = document.getElementById("floatingCartBox");

  if (user && user.role === "admin") {
    cartIcon.style.display = "none";
    cartBox.style.display = "none";
  } else {
    cartIcon.style.display = "block";
  }
}



// চ্যাট ডাটা স্টোরেজ
// key: "chatMessages" in localStorage: array of {sender: "user"|"admin", message: string, date: timestamp, userMobile?:string}

function openChat() {
  document.getElementById("chatWindow").style.display = "flex";
  document.getElementById("chatButton").style.display = "none";
renderChatMessages();
renderUserList();
}
function closeChat() {
  document.getElementById("chatWindow").style.display = "none";
  document.getElementById("chatButton").style.display = "block";
}
function renderChatMessages() {
  const chatDiv = document.getElementById("chatMessages");
  chatDiv.innerHTML = "";

  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user) {
    chatDiv.innerHTML = "<p>অনুগ্রহ করে লগইন করুন চ্যাট করার জন্য।</p>";
    return;
  }

  const allMessages = JSON.parse(localStorage.getItem("chatMessages")) || [];
  let messagesToShow = [];

  if (user.role === "admin") {
    if (selectedUserMobile) {
      messagesToShow = allMessages.filter(
        m => m.userMobile === selectedUserMobile
      );
    } else {
      // ✅ অ্যাডমিনের নিজের মেসেজ, যেগুলোর userMobile = admin এর mobile
      messagesToShow = allMessages.filter(
        m => m.sender === "admin" && m.userMobile === user.mobile
      );
    }
  } else {
    // ✅ সাধারণ ইউজার
    messagesToShow = allMessages.filter(
      m => m.userMobile === user.mobile
    );
  }

  if (messagesToShow.length === 0) {
    chatDiv.innerHTML = "<p>কোনো মেসেজ পাওয়া যায়নি।</p>";
    return;
  }

  messagesToShow.forEach(msg => {
    const div = document.createElement("div");
    div.style.marginBottom = "10px";
    div.style.padding = "6px 10px";
    div.style.borderRadius = "8px";
    div.style.maxWidth = "70%";
    div.style.wordBreak = "break-word";
    div.style.fontSize = "14px";
    div.style.whiteSpace = "pre-wrap";
    div.style.display = "inline-block";

    const wrapper = document.createElement("div");
    wrapper.style.display = "flex";
    wrapper.style.justifyContent = msg.sender === "admin" ? "flex-end" : "flex-start";

    if (msg.sender === "admin") {
      div.style.background = "#cce5ff";
      div.innerHTML = `<strong>🛡️ অ্যাডমিন:</strong><br>${escapeHtml(msg.message)}`;
    } else {
      div.style.background = "#d1ffd6";
      let nameShow =
        user.role === "admin"
          ? `<strong>👤 ${msg.userName || "ইউজার"}:</strong><br>`
          : `<strong>আপনি:</strong><br>`;
      div.innerHTML = nameShow + escapeHtml(msg.message);
    }

    wrapper.appendChild(div);
    chatDiv.appendChild(wrapper);
  });

  chatDiv.scrollTop = chatDiv.scrollHeight;
}
// মেসেজ পাঠানোর হ্যান্ডলার
function sendChatMessage(e) {
  e.preventDefault();

  const input = document.getElementById("chatInput");
  const msg = input.value.trim();
  if (!msg) return;

  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user) {
    alert("❌ অনুগ্রহ করে লগইন করুন চ্যাট করার জন্য।");
    return;
  }

  const newMsg = {
    sender: user.role === "admin" ? "admin" : "user",
    userName: user.name || "ইউজার",
    userMobile: user.mobile,
    message: msg,
    date: new Date().toISOString()
  };

  let allMessages = JSON.parse(localStorage.getItem("chatMessages")) || [];
  allMessages.push(newMsg);
  localStorage.setItem("chatMessages", JSON.stringify(allMessages));

  // ইউজার যদি "অর্ডার" টাইপ করে চ্যাটে
  if (user.role !== "admin" && msg.toLowerCase().includes("অর্ডার")) {
    orders.push({
      name: user.name,
      address: user.address || "নাই",
      mobile: user.mobile,
      userMobile: user.mobile,
      date: new Date().toLocaleString(),
      items: [{ name: "চ্যাট অর্ডার", qty: 1, price: 0, total: 0 }],
      status: "pending",
      chatOrder: true,
      message: msg
    });
    saveOrders();
    alert("✅ আপনার অর্ডার গ্রহণ করা হয়েছে চ্যাট থেকে!");
  }

  input.value = "";
  renderChatMessages();
}

// Escape HTML to avoid injection
function escapeHtml(text) {
  var map = {
    '&': '&amp;',
    '<': '&lt;',
    '>': '&gt;',
    '"': '&quot;',
    "'": '&#039;'
  };
  return text.replace(/[&<>"']/g, function(m) { return map[m]; });
}

// চ্যাট মেসেজগুলো দেখার জন্য অ্যাডমিন বাটন (optional)
if (document.getElementById("adminBtn")) {
  const adminBtn = document.getElementById("adminBtn");
  adminBtn.insertAdjacentHTML("afterend", `<button onclick="openChat()" style="margin-left: 5px;</button>`)
}


function printSingleOrder(index) {
  if (!orders[index]) {
    alert("❌ অর্ডার পাওয়া যায়নি!");
    return;
  }
  const order = orders[index];

  let itemsHtml = "";
  order.items.forEach(item => {
    itemsHtml += `
      <tr>
        <td>${item.name}</td>
        <td style="text-align:center;">${item.qty}</td>
        <td style="text-align:right;">৳${item.price.toFixed(2)}</td>
        <td style="text-align:right;">৳${item.total.toFixed(2)}</td>
      </tr>
    `;
  });

  let totalPrice = order.items.reduce((sum, i) => sum + i.total, 0);

  const html = `
    <html lang="bn">
    <head>
      <meta charset="UTF-8" />
      <title>ইনভয়েস প্রিন্ট - অর্ডার #${index + 1}</title>
      <style>
        body {
          font-family: 'SolaimanLipi', Arial, sans-serif;
          margin: 20px;
          color: #333;
        }
        h2 {
          text-align: center;
          color: #4CAF50;
          margin-bottom: 10px;
        }
        p {
          margin: 4px 0;
          font-size: 14px;
        }
        table {
          width: 100%;
          border-collapse: collapse;
          margin-top: 15px;
          margin-bottom: 20px;
        }
        th, td {
          border: 1px solid #ddd;
          padding: 8px;
          font-size: 14px;
        }
        th {
          background-color: #000000;
          color: white;
        }
        tfoot td {
          font-weight: bold;
          font-size: 16px;
        }
        .center {
          text-align: center;
        }
        .right {
          text-align: right;
        }
        @media print {
          button {
            display: none;
          }
        }
        button.print-btn {
          background-color: #4CAF50;
          color: white;
          border: none;
          padding: 10px 15px;
          font-size: 14px;
          cursor: pointer;
          border-radius: 5px;
          margin-bottom: 15px;
          display: block;
          margin-left: auto;
          margin-right: auto;
        }
      </style>
    </head>
    <body>
    
    
    
    
    
      <button class="print-btn" onclick="window.print()">🖨️ প্রিন্ট করুন</button>
      <h2>ইনভয়েস - অর্ডার #${index + 1}</h2>
      <p><strong>নাম:</strong> ${order.name}</p>
      <p><strong>মোবাইল:</strong> ${order.mobile}</p>
      <p><strong>ঠিকানা:</strong> ${order.address}</p>
      <p><strong>তারিখ:</strong> ${order.date}</p>

      <table>
        <thead>
          <tr>
            <th>পণ্য</th>
            <th class="center">পরিমাণ</th>
            <th class="right">মূল্য (৳)</th>
            <th class="right">মোট (৳)</th>
          </tr>
        </thead>
        <tbody>
          ${itemsHtml}
        </tbody>
        <tfoot>
          <tr>
            <td colspan="3" class="right">মোট মূল্য</td>
            <td class="right">৳${totalPrice.toFixed(2)}</td>
          </tr>
        </tfoot>
      </table>

      <p style="text-align:center; font-size: 12px; color: #777;">ধন্যবাদ, আপনার কেনাকাটা করার জন্য!</p>
    </body>
    </html>
  `;

  const win = window.open('', '', 'width=800,height=600');
  win.document.write(html);
  win.document.close();
}



function printAllOrders() {
  let html = `
    <html lang="bn">
    <head>
      <meta charset="UTF-8" />
      <title>সব অর্ডার প্রিন্ট</title>
      <style>
        body {
          font-family: 'SolaimanLipi', Arial, sans-serif;
          padding: 20px;
        }
        h2 {
          margin-bottom: 10px;
        }
        .print-button {
          display: inline-block;
          background: #4CAF50;
          color: white;
          padding: 6px 12px;
          border: none;
          border-radius: 4px;
          cursor: pointer;
          margin-bottom: 15px;
        }
        table {
          border-collapse: collapse;
          width: 100%;
          margin-bottom: 20px;
        }
        th, td {
          border: 1px solid #ccc;
          padding: 8px;
          text-align: left;
        }
        th {
          background: #f2f2f2;
        }
        @media print {
          .print-button {
            display: none;
          }
        }
      </style>
    </head>
    <body>
      <button class="print-button" onclick="window.print()">🖨️ প্রিন্ট করুন</button>
      <h2>📋 সকল অর্ডার তালিকা</h2>
  `;

  if (orders.length === 0) {
    html += `<p>❌ কোনো অর্ডার পাওয়া যায়নি।</p>`;
  } else {
    orders.slice().reverse().forEach(order => {
      let items = order.items.map(i => `${i.name} (${i.qty}x)`).join(", ");
      let total = order.items.reduce((t, i) => t + i.total, 0);
      html += `
        <table>
          <thead>
            <tr>
              <th>🕒 তারিখ</th>
              <th>👤 নাম</th>
              <th>📱 মোবাইল</th>
              <th>📦 পণ্য</th>
              <th>💰 মোট</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>${order.date}</td>
              <td>${order.name}</td>
              <td>${order.mobile}</td>
              <td>${items}</td>
              <td>৳${total}</td>
            </tr>
          </tbody>
        </table>
      `;
    });
  }

  html += `</body></html>`;

  const win = window.open('', '', 'width=800,height=600');
  win.document.write(html);
  win.document.close();
}


  // প্রাথমিক পণ্য ডাটা    
  let products = JSON.parse(localStorage.getItem("products")) || [
  { id: 1, name: "চাল ১ কেজি", price: 70, stock: 5, category: "খাদ্য" },
  { id: 2, name: "শার্ট", price: 300, stock: 10, category: "বস্ত্র" },
  { id: 3, name: "টিউবওয়েল", price: 5000, stock: 2, category: "বাসস্থান" },
  { id: 4, name: "পেন", price: 15, stock: 100, category: "শিক্ষা" }
];
let orders = JSON.parse(localStorage.getItem("orders")) || [];    function saveOrders() {
localStorage.setItem("orders", JSON.stringify(orders));
}










let selectedUserMobile = null;
let users = JSON.parse(localStorage.getItem("users")) || [];
let favorites = JSON.parse(localStorage.getItem("favorites")) || [];
let cart = JSON.parse(localStorage.getItem("cart")) || {};

function saveProducts() {
localStorage.setItem("products", JSON.stringify(products));
}
function saveUsers() {
localStorage.setItem("users", JSON.stringify(users));
}
function saveCart() {
localStorage.setItem("cart", JSON.stringify(cart));
}
function showWelcome() {displayProducts();  // সার্চ ছাড়াই সব পণ্য দেখাবে






  const user = JSON.parse(localStorage.getItem("loggedInUser"));

  if (user) {
    document.getElementById("authBox").style.display = "none";
    document.getElementById("storeBox").style.display = "block";
    document.getElementById("userInfoBox").style.display = "block";

    document.getElementById("userNameDisplay").textContent = user.name;
    document.getElementById("userMobileDisplay").textContent = user.mobile;

    

    const adminBtn = document.getElementById("adminBtn");


if (user.role === "admin") {
  // অ্যাডমিনের জন্য ইউজার পণ্য লিস্ট লুকাও
  const myOrdersBtn = document.getElementById("myOrdersBtn");

if (user.role === "user") {
    myOrdersBtn.style.display = "inline-block";
} else {
    myOrdersBtn.style.display = "none";
}
  
  const userProductSection = document.getElementById("userOnlyProducts");
  if (userProductSection) userProductSection.style.display = "none";
}


    if (user.role === "admin") {
      adminBtn.style.display = "inline-block";
      document.getElementById("orderForm").style.display = "none";
      document.getElementById("userHistoryBtn").style.display = "inline-block";
      document.getElementById("orderTitle").style.display = "none";
      document.getElementById("adminDashboard").style.display = "block";
      renderAdminDashboard();
      renderAdminList();
    } else {
      adminBtn.style.display = "none";
      document.getElementById("orderForm").style.display = "block";
      document.getElementById("orderTitle").style.display = "block";
      document.getElementById("adminDashboard").style.display = "none";
    }

    displayProducts();
    renderFloatingCart();

  } else {
    document.getElementById("authBox").style.display = "block";
    document.getElementById("storeBox").style.display = "none";
    document.getElementById("userInfoBox").style.display = "none";
    controlFloatingCartVisibility();
  }
}


function showRegister() {
document.getElementById("loginForm").style.display = "none";
document.getElementById("registerForm").style.display = "block"
}
function showMyAccount() {
  const box = document.getElementById("myAccountBox");
if (box.style.display === "block") {
  box.style.display = "none";
  return;
}
  
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user) {
    alert("❌ লগইন করা হয়নি");
    return;
  }

  document.getElementById("editName").value = user.name || "";
  document.getElementById("editMobile").value = user.mobile || "";
  document.getElementById("editAddress").value = user.address || "";
  document.getElementById("editPassword").value = user.password || "";

  document.getElementById("myAccountBox").style.display = "block";
}

function saveProfile() {
  const name = document.getElementById("editName").value.trim();
  const mobile = document.getElementById("editMobile").value.trim();
  const address = document.getElementById("editAddress").value.trim();
  const password = document.getElementById("editPassword").value.trim();

  if (!name || !mobile || !password) {
    alert("❗ নাম, মোবাইল ও পাসওয়ার্ড আবশ্যক!");
    return;
  }

  const updatedUser = {
    name,
    mobile,
    address,
    password,
    role: "user"
  };

  localStorage.setItem("loggedInUser", JSON.stringify(updatedUser));
  alert("✅ প্রোফাইল আপডেট হয়েছে!");
  document.getElementById("myAccountBox").style.display = "none";
}

function showLogin() {
document.getElementById("loginForm").style.display = "block";
document.getElementById("registerForm").style.display = "none";
}
function register() {
  const mobile = document.getElementById("regMobile").value.trim();
// মোবাইল নম্বর চেক করার জন্য regex
const mobilePattern = /^01\d{9}$/;

if (!mobilePattern.test(mobile)) {
  alert("সঠিক মোবাইল নম্বর দিন (যেমন: 01XXXXXXXXX), মোট ১১ অঙ্কের হতে হবে।");
  return;
}
const name = document.getElementById("regName").value.trim();
const address = document.getElementById("regAddress").value.trim();
const pass = document.getElementById("regPass").value;
const role = document.getElementById("regRole").value;

if (!name || !mobile || !pass || !address) {
    alert("সব ঘর পূরণ করুন");
    return;} 
    
if (users.find(u => u.mobile === mobile)) {    
  alert("এই মোবাইল নম্বর আগে থেকে ব্যবহার করা হয়েছে");    
  return;    
}    
users.push({ name, mobile, pass, role, address});

// যদি রোল অ্যাডমিন হয়, তাহলে সিক্রেট কোড চেক করবে
if (role === "admin") {
const adminSecret = prompt("⚠️ অ্যাডমিন কোড দিন:");
if (adminSecret !== "1") {

alert("❌ ভুল অ্যাডমিন কোড! রেজিস্ট্রেশন বাতিল করা হয়েছে।");    
return;

}
}
saveUsers();
alert("✅ সফলভাবে রেজিস্ট্রেশন সম্পন্ন হয়েছে। এখন লগইন করুন।");
showLogin();
}
function login() {
const mobile = document.getElementById("loginMobile").value.trim();
const pass = document.getElementById("loginPass").value;
const user = users.find(u => u.mobile === mobile && u.pass === pass);
if (!user) {
alert("❌ ভুল মোবাইল অথবা পাসওয়ার্ড");
return;
}
localStorage.setItem("loggedInUser", JSON.stringify(user));
showWelcome();
location.reload();
}
function logout() {
localStorage.removeItem("loggedInUser");
showWelcome();
}
function filterByCategory() {
  const selected = document.getElementById("categoryFilter").value;
  const searchText = document.getElementById("searchBox").value.trim();
  displayProducts(searchText, selected);
}
document.getElementById("searchBox").addEventListener("input", (e) => {
  const category = document.getElementById("categoryFilter").value;
  displayProducts(e.target.value, category);
});


function changeStock(id, delta) {
const product = products.find(p => p.id === id);
if (!product) return;

product.stock += delta;    
if (product.stock < 0) product.stock = 0;    

saveProducts();    
displayProducts(document.getElementById("searchBox").value);    
renderAdminList();

}

function addToCart(id) {
const product = products.find(p => p.id === id);
if (!product) return;

if (!cart[id]) cart[id] = 0;    
if (cart[id] < product.stock) {    
  cart[id]++;    
  saveCart();    

  renderFloatingCart();    
} else {    
  alert("স্টক সীমা ছাড়িয়ে গেছে!");    
}

}

function renderProductList() {
  const container = document.getElementById("productList");
  container.innerHTML = "";
  const products = JSON.parse(localStorage.getItem("products")) || [];

  products.forEach((product, index) => {
    const div = document.createElement("div");
    div.innerHTML = `
      <h3>${product.name}</h3>
      <img src="${product.image}" width="100" alt="পণ্যের ছবি"><br>
      <strong>মূল্য:</strong> ${product.price} টাকা<br>
      <button onclick="addToCart(${index})">🛒 কার্টে যোগ করুন</button>
    `;
    container.appendChild(div);
  });
}



function toggleFavorite(id) {
if (favorites.includes(id)) {
favorites = favorites.filter(f => f !== id);
} else {
favorites.push(id);
}
localStorage.setItem("favorites", JSON.stringify(favorites));
displayProducts(document.getElementById("searchBox").value);
}




function submitOrder(e) {
  e.preventDefault();
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user) {
    alert("❌ অনুগ্রহ করে লগইন করুন অর্ডার দিতে।");
    return;
  }

  // ইউজারের তথ্য সরাসরি নিয়ে নিচ্ছি
  const name = user.name;
  const address = user.address || "নাই";
  const mobile = user.mobile;

  if (!name || !mobile) {
    alert("আপনার ইউজার প্রোফাইলে নাম এবং মোবাইল অবশ্যই থাকতে হবে।");
    return;
  }

  if (Object.keys(cart).length === 0) {
    alert("আপনার কার্ট খালি!");
    return;
  }

  // কার্টের পণ্যগুলো থেকে অর্ডারের আইটেম তৈরি করবো
  const items = Object.entries(cart).map(([id, qty]) => {
    const product = products.find(p => p.id == id);
    return {
      id,
      name: product.name,
      qty,
      price: product.price,
      total: product.price * qty
    };
  });

  // অর্ডার অবজেক্ট তৈরি
  orders.push({
    name,
    address,
    mobile,
    userMobile: user.mobile,
    date: new Date().toLocaleString(),
    items,
    status: "pending"
  });

  saveOrders();

  // কার্ট খালি করে সেভ করবো
  cart = {};
  saveCart();

  alert(`✅ ধন্যবাদ ${name}! আপনার অর্ডার গ্রহণ করা হয়েছে।`);

  e.target.reset();
  renderFloatingCart();
}

function toggleAdmin() {
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user || user.role !== "admin") {
    alert("❌ শুধুমাত্র অ্যাডমিন প্যানেল দেখতে পারবেন!");
    return;
  }
  const panel = document.getElementById("adminPanel");
  panel.style.display = panel.style.display === "none" ? "block" : "none";
renderAdminList();

}

// ইউজার হিস্টোরি বাটনে ক্লিক করলে ইউজার লিস্ট 
document.getElementById("userHistoryBtn").onclick = function() {
  toggleUserBox();
}


function addNewProduct() {
  const name = document.getElementById("adminName").value.trim();
  const price = parseInt(document.getElementById("adminPrice").value);
  const stock = parseInt(document.getElementById("adminStock").value);
  const category = document.getElementById("adminCategory").value;
 const imageInput = document.getElementById("productImage");


  if (!name || !price || !stock || !category) {
    alert("সব ঘর পূরণ করুন (নাম, দাম, স্টক, ক্যাটাগরি)।");
    return;
  }

  if (!imageInput.files.length) {
    alert("✅ পণ্যের একটি ছবি নির্বাচন করুন");
    return;
  }

  const reader = new FileReader();

  reader.onload = function (e) {
    const image = e.target.result;
    const id = Date.now();

    products.push({ id, name, price, stock, category, image });
    saveProducts();
    displayProducts();
    renderAdminList();

    alert("✅ পণ্য সফলভাবে যোগ হয়েছে");

    // ইনপুটগুলো রিসেট করো
    document.getElementById("adminName").value = "";
    document.getElementById("adminPrice").value = "";
    document.getElementById("adminStock").value = "";
    document.getElementById("adminCategory").value = "";
    document.getElementById("adminImage").value = "";
  };

  reader.readAsDataURL(imageInput.files[0]);
}

function renderAdminDashboard() {
  document.getElementById("totalUsers").textContent = users.length;
  document.getElementById("totalOrders").textContent = orders.length;

  const list = document.getElementById("dashboardProductList");
  list.innerHTML = "";
  products.forEach(p => {
    const li = document.createElement("li");
    li.textContent = `${p.name} - দাম: ৳${p.price}, স্টক: ${p.stock}`;
    list.appendChild(li);
  });
}

function renderAdminList() {
const list = document.getElementById("adminProductList");
list.innerHTML = "";
products.forEach(p => {
const li = document.createElement("li");
li.innerHTML = `${p.name} (৳${p.price}, স্টক: ${p.stock}) <button onclick="editProduct(${p.id})">✏️</button> 
<button onclick="deleteProduct(${p.id})">🗑️</button>
<button onclick="imageInputProduct(${p.id})">📸</button>
`;
list.appendChild(li);
});
}

function editProduct(id) {
    const p = products.find(p => p.id === id);
    if (!p) return;

    // নতুন দাম নেওয়া
    const newPrice = parseInt(prompt("নতুন দাম:", p.price));    
    if (isNaN(newPrice)) return;    

    // নতুন স্টক নেওয়া
    const newStock = parseInt(prompt("নতুন স্টক:", p.stock));    
    if (isNaN(newStock)) return;    

    // নতুন নাম নেওয়া
    const newName = prompt("নতুন নাম:", p.name);
    if (!newName) return;

    // পণ্যের তথ্য আপডেট
    p.price = newPrice;
    p.stock = newStock;
    p.name = newName;

    // পণ্য সংরক্ষণ
    saveProducts();
    
    // প্রোডাক্ট তালিকা রেন্ডার করা
    displayProducts();
    renderAdminList();
}

function imageInputProduct(id) {
  const input = document.createElement("input");
  input.type = "file";
  input.accept = "image/*";
  input.style.display = "none";

  input.addEventListener("change", function () {
    if (!input.files.length) return;
    const file = input.files[0];
    const reader = new FileReader();

    reader.onload = function (e) {
      const product = products.find(p => p.id === id);
      if (!product) {
        alert("❌ পণ্য খুঁজে পাওয়া যায়নি।");
        return;
      }
      product.image = e.target.result;
      saveProducts();
      displayProducts();
      renderAdminList();
      alert("✅ পণ্যের ছবি আপডেট হয়েছে!");
    };

    reader.readAsDataURL(file);
  });

  document.body.appendChild(input);
  input.click();
  document.body.removeChild(input);
}

function deleteProduct(id) {
if (!confirm("পণ্য মুছে ফেলতে চান?")) return;

products = products.filter(p => p.id !== id);    
saveProducts();    
displayProducts();    
renderAdminList();

}

// Change Password
function showChangePassword() {
document.getElementById("changePasswordBox").style.display = "block";
}

function changePassword() {
const oldPass = document.getElementById("oldPass").value;
const newPass = document.getElementById("newPass").value;

if (!oldPass || !newPass) {    
  alert("সব ঘর পূরণ করুন");    
  return;    
}    

let user = JSON.parse(localStorage.getItem("loggedInUser"));    
if (!user) return;    

if (oldPass !== user.pass) {    
  alert("পুরানো পাসওয়ার্ড ভুল");    
  return;    
}    

user.pass = newPass;    
localStorage.setItem("loggedInUser", JSON.stringify(user));    

let idx = users.findIndex(u => u.mobile === user.mobile);    
if (idx !== -1) {    
  users[idx].pass = newPass;    
  saveUsers();    
}    

alert("পাসওয়ার্ড সফলভাবে পরিবর্তন হয়েছে");    
document.getElementById("changePasswordBox").style.display = "none";    
document.getElementById("oldPass").value = "";    
document.getElementById("newPass").value = "";

}

// Floating Cart Toggle
function toggleFloatingCart() {
const box = document.getElementById("floatingCartBox");
box.style.display = (box.style.display === "block") ? "none" : "block";
}

function cancelUserOrder(index) {
  if (!confirm("আপনি কি নিশ্চিত অর্ডারটি বাতিল করতে চান?")) return;

  const orders = JSON.parse(localStorage.getItem("orders")) || [];
  if (!orders[index]) {
    alert("❌ অর্ডার খুঁজে পাওয়া যায়নি!");
    return;
  }

  if (orders[index].status === "pending" || orders[index].status === "received") {
    orders.splice(index, 1);
    localStorage.setItem("orders", JSON.stringify(orders));
    alert("✅ অর্ডার বাতিল করা হয়েছে।");
    document.getElementById("myOrdersModal").remove();
    showMyOrders(); // রিফ্রেশ
  } else {
    alert("❌ অর্ডার বাতিল করা যাবে না কারণ এটি প্রক্রিয়াধীন।");
  }
}

function showMyOrders() {
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user || user.role !== "user") {
    alert("❌ শুধুমাত্র লগইনকৃত ইউজাররা মাই অর্ডার দেখতে পারবে।");
    return;
  }

  const orders = JSON.parse(localStorage.getItem("orders")) || [];
  const userOrders = orders.filter(o => o.userMobile === user.mobile);

  const orderList = userOrders.map((order, index) => {
    const items = order.items.map(i => `${i.name} (${i.qty}x)`).join(", ");
    const total = order.items.reduce((t, i) => t + (i.total || 0), 0);

    const canCancel = order.status === "pending" || order.status === "received";
    const cancelButton = canCancel
      ? `<button onclick="cancelUserOrder(${orders.indexOf(order)})">❌ ক্যানসেল</button>`
      : `<span style="color:gray;">❌ ক্যানসেল করা যাবে না</span>`;

    return `
      <li style="border:1px solid #ccc; margin-bottom:10px; padding:8px; border-radius:6px; background:#fff;">
        🕒 ${order.date}<br>
        🛍️ ${items}<br>
        💰 মোট: ৳${total}<br>
        🔄 অবস্থা: <strong>${order.status || "pending"}</strong><br>
        ${cancelButton}
      </li>
    `;
  }).join("");

  const modal = document.createElement("div");
  modal.id = "myOrdersModal";
  modal.style.position = "fixed";
  modal.style.top = "0";
  modal.style.left = "0";
  modal.style.width = "100%";
  modal.style.height = "100%";
  modal.style.background = "rgba(0,0,0,0.5)";
  modal.style.zIndex = "10000";
  modal.style.overflowY = "auto";
  modal.style.padding = "20px";
  modal.innerHTML = `
    <div style="max-width:500px; background:#f9f9f9; margin:auto; padding:20px; border-radius:8px; position:relative;">
      <button onclick="document.getElementById('myOrdersModal').remove()" style="position:absolute; top:10px; right:10px; background:#e53935; color:white; border:none; padding:6px 10px; border-radius:4px;">✖</button>
<button onclick="printMyOrders()">🖨️ অর্ডার প্রিন্ট করুন</button>
      <h3 style="margin-top:0;">📦 আপনার অর্ডারসমূহ</h3>
<div id="myOrdersCaptureArea">
  <ul style="list-style:none; padding:0; font-size:14px;"> </div>
        ${userOrders.length ? orderList : "<li>❌ কোনো অর্ডার পাওয়া যায়নি।</li>"}
      </ul>
    </div>
  `;
  document.body.appendChild(modal);
}
// Render Floating Cart
function renderFloatingCart() {
const container = document.getElementById("floatingCartItems");
container.innerHTML = "";

const cartKeys = Object.keys(cart);    
if (cartKeys.length === 0) {    
  container.textContent = "কার্ট খালি";    
  document.getElementById("floatingCartTotal").textContent = "0";    
  return;    
}    

let total = 0;    

cartKeys.forEach(id => {    
  const product = products.find(p => p.id == id);    
  if (!product) return;    

  const qty = cart[id];    
  total += product.price * qty;    

  const div = document.createElement("div");    
  div.className = "cart-item";    

  div.innerHTML = `    
    <span>${product.name}</span>    
    <div>    
      <button onclick="decreaseQty(${id})" ${qty <= 1 ? "disabled" : ""}>➖</button>    
      <span>${qty}</span>    
      <button onclick="increaseQty(${id})" ${qty >= product.stock ? "disabled" : ""}>➕</button>    
      <button onclick="removeFromCart(${id})">❌</button>    
    </div>    
    
    
    
    
  `;    

  container.appendChild(div);    
});    

document.getElementById("floatingCartTotal").textContent = total;


}  


function increaseQty(id) {
const product = products.find(p => p.id == id);
if (!product) return;

if (cart[id] < product.stock) {
cart[id]++;
saveCart();
renderFloatingCart();
} else {
alert("স্টক ছাড়িয়ে গেছে!");
}

}

// Decrease quantity in cart
function decreaseQty(id) {
if (!cart[id]) return;
cart[id]--;
if (cart[id] <= 0) delete cart[id];
saveCart();
renderFloatingCart();
}

// Rr product from cart
function removeFromCart(id) {
delete cart[id];
saveCart();
renderFloatingCart();
}

// Search box event
document.getElementById("searchBox").addEventListener("input", (e) => {
displayProducts(e.target.value);
});


function renderUserList() {
  const userListDiv = document.getElementById("userList");
  if (!userListDiv) return;

  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user || user.role !== "admin") {
    userListDiv.innerHTML = "";
    return;
  }

  const allMessages = JSON.parse(localStorage.getItem("chatMessages")) || [];

  // শুধু যেসব ইউজার মেসেজ দিয়েছে তাদের mobile আলাদা করে নিই
  const userMobiles = [...new Set(allMessages.filter(m => m.sender === "user").map(m => m.userMobile))];

  userListDiv.innerHTML = "<h4>🧾 ইউজার তালিকা</h4>";
  userMobiles.forEach(mobile => {
    const btn = document.createElement("button");
    btn.textContent = `👤 ${mobile}`;
    btn.style.margin = "4px";
    btn.style.padding = "6px 10px";
    btn.style.cursor = "pointer";
    btn.style.border = "1px solid #4CAF50";
    btn.style.borderRadius = "6px";
    btn.style.background = mobile === selectedUserMobile ? "#aaffaa" : "#fff";
    btn.onclick = () => {
      selectedUserMobile = mobile;
      renderChatMessages();
      renderUserList(); // রিফ্রেশ
    };
    userListDiv.appendChild(btn);
  });
}




// ইউজার লিস্ট দেখানোর ফাংশন

// ইউজার ডিলিট করার ফাংশন
function deleteUser(index) {
  if (!confirm("আপনি কি নিশ্চিত ইউজারটি মুছে ফেলতে চান?")) return;

  users.splice(index, 1);
  saveUsers();
  renderAdminUserList();

  alert("✅ ইউজার মুছে ফেলা হয়েছে");
}
const user = JSON.parse(localStorage.getItem("loggedInUser"));
const searchBoxSection = document.getElementById("searchFilterBox");

if (user && user.role === "admin") {
  if (searchBoxSection) {
    searchBoxSection.style.display = "none";
  }
}

window.onload = function () {
    // এডমিন হলে বাটন দেখাও
    const user = JSON.parse(localStorage.getItem("loggedInUser"));
    if (user && user.role === "admin") {
        document.getElementById("userHistoryBtn").style.display = "inline-block";
    }

    showWelcome();
    renderChatMessages();
    renderUserList();
};

// আগে ছিল:
// document.getElementById("userHistoryBtn").onclick = function() { renderAdminUserList() }
// এটি বদলে লিখুন:
document.getElementById("userHistoryBtn").onclick = function() {
   toggleUserBox();
};

function printMyOrders() {
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (!user || user.role !== "user") {
    alert("❌ অনুগ্রহ করে লগইন করুন এবং ইউজার হিসেবে থাকুন।");
    return;
  }

  const orders = JSON.parse(localStorage.getItem("orders")) || [];
  const userOrders = orders.filter(o => o.userMobile === user.mobile);

  if (userOrders.length === 0) {
    alert("❌ কোনো অর্ডার পাওয়া যায়নি, প্রিন্ট করা যাবে না।");
    return;
  }

  let html = `
    <html lang="bn">
    <head>
      <meta charset="UTF-8" />
      <title>আমার অর্ডারসমূহ</title>
      <style>
        body {
          font-family: 'SolaimanLipi', Arial, sans-serif;
          padding: 20px;
          color: #333;
        }
        h2 {
          text-align: center;
          color: #4CAF50;
          margin-bottom: 10px;
        }
        table {
          width: 100%;
          border-collapse: collapse;
          margin-bottom: 15px;
        }
        th, td {
          border: 1px solid #ddd;
          padding: 8px;
          font-size: 14px;
        }
        th {
          background: #4CAF50;
          color: white;
        }
        .print-button {
          display: block;
          margin: 10px auto;
          padding: 8px 12px;
          background: #4CAF50;
          color: white;
          border: none;
          border-radius: 4px;
          font-size: 14px;
          cursor: pointer;
        }
        @media print {
          .print-button {
            display: none;
          }
        }
      </style>
    </head>
    <body>
      <button class="print-button" onclick="window.print()">🖨️ প্রিন্ট করুন</button>
      <h2>📋 আমার অর্ডারসমূহ</h2>
  `;

  userOrders.forEach((order, index) => {
    let items = order.items.map(i => `${i.name} (${i.qty}x)`).join(", ");
    let total = order.items.reduce((t, i) => t + (i.total || 0), 0);

    html += `
      <table>
        <thead>
          <tr>
            <th>তারিখ</th>
            <th>পণ্যসমূহ</th>
            <th>মোট মূল্য (৳)</th>
            <th>অবস্থা</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>${order.date}</td>
            <td>${items}</td>
            <td>৳${total}</td>
            <td>${order.status || "pending"}</td>
          </tr>
        </tbody>
      </table>
    `;
  });

  html += `
      <p style="text-align:center; font-size: 13px; color: #777;">ধন্যবাদ, আপনার অর্ডারের জন্য।</p>
    </body>
    </html>
  `;

  const printWindow = window.open("", "", "width=800,height=600");
  printWindow.document.write(html);
  printWindow.document.close();
}
function submitOrderManually() {
  submitOrder({ preventDefault: () => {} });
}





// Show order form only for non-admin users
window.addEventListener("DOMContentLoaded", function () {
  const user = JSON.parse(localStorage.getItem("loggedInUser"));
  if (user && user.role !== "admin") {
    const form = document.getElementById("orderForm");
    if (form) form.style.display = "block";
  }
});

function clearCart() {
  if (confirm("আপনি কি নিশ্চিত কার্ট খালি করতে চান?")) {
    cart = {};
    saveCart();
    renderFloatingCart();
  }
}

function filterOrdersByStatus() {
  viewAllOrders();
  const selected = document.getElementById("statusFilter").value;
  const list = document.getElementById("allOrderList");
  const allOrders = JSON.parse(localStorage.getItem("orders")) || [];

  list.innerHTML = "";
  allOrders.slice().reverse().forEach((order, index) => {
    if (!selected || order.status === selected) {
      const actualIndex = allOrders.length - 1 - index;
      const li = document.createElement("li");
      let items = order.items.map(i => `${i.name} (${i.qty}x)`).join(", ");
      let total = order.items.reduce((t, i) => t + (i.total || 0), 0);

      li.innerHTML = `
        🕒 ${order.date} | 👤 ${order.name} (${order.userMobile})<br>
        🛍️ ${items} | 💰 মোট: ৳${total}<br>
        🔄 অবস্থা: <strong>${order.status || "pending"}</strong><br>
        <button onclick="updateOrderStatus(${actualIndex}, 'received')">✅ গ্রহণ</button>
        <button onclick="updateOrderStatus(${actualIndex}, 'cancelled')">❌ বাতিল</button>
        <button onclick="updateOrderStatus(${actualIndex}, 'sent')">🚚 পাঠানো</button>
        <button onclick="updateOrderStatus(${actualIndex}, 'delivered')">📦 ডেলিভারি</button>
        <button onclick="printSingleOrder(${actualIndex})">🖨️ প্রিন্ট</button>
      `;
      li.style.marginBottom = "15px";
      li.style.padding = "10px";
      li.style.background = "#000000";
      li.style.borderRadius = "6px";
      list.appendChild(li);
    }
  });

  if (!list.innerHTML) {
    list.innerHTML = "<li>❌ কোনো অর্ডার পাওয়া যায়নি।</li>";
  }
}

function generateSalesSummary() {
  const orders = JSON.parse(localStorage.getItem("orders")) || [];
  const monthlySales = {};

  orders.forEach(order => {
    const month = new Date(order.date).toLocaleString("bn-BD", { year: "numeric", month: "long" });
    const total = order.items.reduce((sum, item) => sum + (item.total || 0), 0);
    if (!monthlySales[month]) monthlySales[month] = 0;
    monthlySales[month] += total;
  });

  const container = document.getElementById("salesChart");
  if (!container) return;

  if (Object.keys(monthlySales).length === 0) {
    container.innerHTML = "<p>❌ এখনো কোনো অর্ডার পাওয়া যায়নি।</p>";
    return;
  }

  let table = "<table style='width:100%; border-collapse:collapse;'><thead><tr><th style='border:1px solid #ccc; padding:6px;'>মাস</th><th style='border:1px solid #ccc; padding:6px;'>মোট বিক্রি (৳)</th></tr></thead><tbody>";
  for (const month in monthlySales) {
    table += `<tr><td style='border:1px solid #ccc; padding:6px;'>${month}</td><td style='border:1px solid #ccc; padding:6px;'>৳${monthlySales[month].toFixed(2)}</td></tr>`;
  }
  table += "</tbody></table>";

  container.innerHTML = table;
}

window.addEventListener("DOMContentLoaded", generateSalesSummary);

let currentChatUser = null;

function renderUserChatList() {
  const messages = JSON.parse(localStorage.getItem("messages")) || [];
  const userMap = {};

  messages.forEach(msg => {
    if (!userMap[msg.mobile]) {
      userMap[msg.mobile] = msg;
    }
  });

  const list = document.getElementById("userChatList");
  list.innerHTML = "";

  Object.values(userMap).forEach(user => {
    const li = document.createElement("li");
    li.style.padding = "6px";
    li.style.borderBottom = "1px solid #ccc";
    li.style.cursor = "pointer";
    li.textContent = `${user.name} (${user.mobile})`;
    li.onclick = () => {
      currentChatUser = user.mobile;
      renderAdminChat();
    };
    list.appendChild(li);
  });
}

function renderAdminChat() {
  const messageList = document.getElementById("adminMessageList");
  const messages = JSON.parse(localStorage.getItem("messages")) || [];

  const filtered = messages.filter(m => m.mobile === currentChatUser);
  messageList.innerHTML = "";

  filtered.forEach(msg => {
    const div = document.createElement("div");
    div.style.margin = "6px 0";
    div.style.textAlign = msg.sender === "admin" ? "right" : "left";
    div.innerHTML = `<span style="background:${msg.sender === "admin" ? "#d1f5d3" : "#f0f0f0"}; padding:6px 10px; border-radius:10px; display:inline-block;">${msg.message}</span>`;
    messageList.appendChild(div);
  });

  messageList.scrollTop = messageList.scrollHeight;
}

function sendAdminMessage(e) {
  e.preventDefault();
  const input = document.getElementById("adminMessageInput");
  const message = input.value.trim();
  if (!message || !currentChatUser) return;

  const messages = JSON.parse(localStorage.getItem("messages")) || [];
  messages.push({
    mobile: currentChatUser,
    message,
    sender: "admin",
    date: new Date().toLocaleString()
  });

  localStorage.setItem("messages", JSON.stringify(messages));
  input.value = "";
  renderAdminChat();
}

window.addEventListener("DOMContentLoaded", renderUserChatList);

function previewProductImage(event) {
  const file = event.target.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    const preview = document.getElementById("productImagePreview");
    preview.src = e.target.result;
    preview.style.display = "block";
  };
  reader.readAsDataURL(file);
}

// Override addProduct to include uploaded image
function addProduct(e) {
  e.preventDefault();
  const name = document.getElementById("productName").value.trim();
  const price = parseFloat(document.getElementById("productPrice").value);
  const stock = parseInt(document.getElementById("productStock").value);
  const imageFile = document.getElementById("productImageInput").files[0];

  if (!name || isNaN(price) || isNaN(stock)) {
    alert("❗ সকল তথ্য দিন");
    return;
  }

  const reader = new FileReader();
  reader.onload = function(event) {
    const image = event.target.result;
    const newProduct = {
      id: Date.now(),
      name,
      price,
      stock,
      image
    };
    products.push(newProduct);
    saveProducts();
    renderProducts();
    e.target.reset();
    document.getElementById("productImagePreview").style.display = "none";
  };

  if (imageFile) {
    reader.readAsDataURL(imageFile);
  } else {
    const newProduct = {
      id: Date.now(),
      name,
      price,
      stock,
      image: "https://via.placeholder.com/150"
    };
    products.push(newProduct);
    saveProducts();
    renderProducts();
    e.target.reset();
    document.getElementById("productImagePreview").style.display = "none";
  }
}
</script>

<!-- যদি কোনও div খোলা থাকে, তাহলে এখানে বন্ধ করা যেতে পারে -->
</div> <!-- যদি উপরের কোথাও <div> খোলা থাকে -->


</body>
</html>
