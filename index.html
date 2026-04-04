<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Deenify</title>

<style>
body {
    font-family: Arial;
    text-align: center;
    background: linear-gradient(135deg, #e0f7fa, #fce4ec);
    margin: 0;
}

h1 { margin-top: 20px; }

#searchBox {
    padding: 14px;
    width: 85%;
    max-width: 400px;
    border-radius: 30px;
    border: none;
    margin: 20px;
}

#adminPanel {
    display: none;
    background: white;
    padding: 20px;
    margin: 20px;
    border-radius: 15px;
}

#products {
    display: grid;
    grid-template-columns: repeat(2,1fr);
    gap: 10px;
    padding: 10px;
}

.product {
    background: white;
    padding: 10px;
    border-radius: 10px;
}

.product img {
    width: 40%;
    height: 50px;
    object-fit: contain;
    border-radius: 8px;
    display: block;
    margin: auto;
}

.buy {
    background: red;
    color: white;
    padding: 10px;
    border: none;
    width: 100%;
    margin-top: 5px;
    border-radius: 8px;
}

.add {
    background: green;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 8px;
}

.deleteBtn {
    background: black;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 8px;
}

.logout {
    background: gray;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 8px;
    margin-top: 10px;
}
</style>
</head>

<body>

<h1>🛒 Deenify</h1>

<!-- 👀 زر مخفي -->
<button onclick="toggleAdmin()" style="opacity:0;position:fixed;top:0;left:0;width:120px;height:120px;"></button>

<input id="searchBox" placeholder="Chercher / Search..." onkeyup="searchLocal()">

<div id="adminPanel">
    <h3>Add Product</h3>

    <input id="name" placeholder="Product name"><br><br>
    <input id="image" placeholder="Image URL"><br><br>
    <input id="link" placeholder="Buy link"><br><br>

    <button class="add" onclick="addProduct()">Add</button>

    <hr>

    <h3>Delete Product</h3>
    <input id="deleteId" placeholder="Product ID"><br><br>
    <button class="deleteBtn" onclick="deleteProduct()">Delete</button>

    <br><br>
    <button class="logout" onclick="logout()">Logout</button>
</div>

<div id="products"></div>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<script>
const client = supabase.createClient(
"https://nuwopwcqxewkdazylanb.supabase.co",
"sb_publishable_F53GV8lPIEHfYb8hPT17SA_wH-7-t2r"
);

let allProducts = [];
let isAdmin = false;
let tapCount = 0;

// 👀 15 ضغطة
function toggleAdmin(){
    tapCount++;
    if(tapCount >= 15){
        tapCount = 0;
        showLogin();
    }
}

// 🔐 login
function showLogin(){
    let email = prompt("Enter email:");
    let password = prompt("Enter password:");
    login(email, password);
}

async function login(email, password){
    const { error } = await client.auth.signInWithPassword({ email, password });

    if(error){
        alert("Wrong login ❌");
        return;
    }

    isAdmin = true;
    document.getElementById("adminPanel").style.display = "block";
    loadProducts();
}

// 🔒 logout
async function logout(){
    await client.auth.signOut();
    isAdmin = false;
    document.getElementById("adminPanel").style.display = "none";
}

// 📦 load
async function loadProducts(){
    const { data } = await client.from("products").select("*");
    allProducts = data || [];
    displayProducts(allProducts);
}

// 🖼 display
function displayProducts(products){
    let html = "";

    products.forEach(p=>{
        html += `
        <div class="product">
            <h4>${p.name}</h4>
            <img src="${p.image}">
            <button class="buy" onclick="window.open('${p.link}')">Buy Now</button>
        </div>`;
    });

    document.getElementById("products").innerHTML = html;
}

// ➕ add
async function addProduct(){
    let name = document.getElementById("name").value;
    let image = document.getElementById("image").value;
    let link = document.getElementById("link").value;

    if(!name || !image || !link){
        alert("Fill all fields");
        return;
    }

    await client.from("products").insert([{name, image, link}]);

    document.getElementById("name").value = "";
    document.getElementById("image").value = "";
    document.getElementById("link").value = "";

    loadProducts();
}

// ❌ delete
async function deleteProduct(){
    let id = document.getElementById("deleteId").value;

    if(!id){
        alert("Enter ID");
        return;
    }

    await client.from("products").delete().eq("id", id);

    document.getElementById("deleteId").value = "";
    loadProducts();
}

// 🔥 normalize
function normalize(text){
    return text
        .toLowerCase()
        .normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "")
        .replace(/[أإآ]/g, "ا")
        .replace(/ة/g, "ه")
        .replace(/ى/g, "ي")
        .trim();
}

// 🌍 dictionary
const dictionary = {
    charger: ["chargeur", "شاحن"],
    phone: ["telephone", "téléphone", "هاتف"],
    laptop: ["ordinateur", "حاسوب"],
    watch: ["montre", "ساعة"],
    headphones: ["ecouteurs", "écouteurs", "سماعات"],
    camera: ["camera", "كاميرا"],
    tablet: ["tablette", "تابلت"],
};

// 🔍 search
function searchLocal(){
    let value = normalize(document.getElementById("searchBox").value);

    let filtered = allProducts.filter(p => {
        let name = normalize(p.name);

        if(name.includes(value)) return true;

        for(let key in dictionary){
            let words = [key, ...dictionary[key]];

            if(words.includes(value)){
                if(words.some(w => name.includes(normalize(w)))){
                    return true;
                }
            }
        }

        return false;
    });

    displayProducts(filtered);
}

// تشغيل
loadProducts();
</script>

</body>
</html>
