# my-allinone-app<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<title>JKS Group Multi-Module Platform</title>
<style>
  body {
    background: #20242b;
    color: #fff;
    font-family: 'Segoe UI', Arial, sans-serif;
    margin: 0; padding: 0;
  }
  header {
    background: #141b29;
    color: #00e1ff;
    font-size: 2.3rem;
    font-weight: 700;
    letter-spacing: 2px;
    padding: 20px 0;
    text-align: center;
    text-shadow: 0 0 22px #0fccfcbb;
  }
  nav {
    display: flex;
    justify-content: center;
    gap: 14px;
    padding: 10px 0;
    background: #141b29;
    border-bottom: 2px solid #00e1ff;
  }
  nav button {
    background: none;
    border: 2.5px solid #0fccfc;
    border-radius: 10px;
    color: #0fccfc;
    cursor: pointer;
    font-weight: 700;
    padding: 12px 22px;
    font-size: 1rem;
    user-select: none;
    transition: all 0.3s ease;
  }
  nav button:hover {
    background: #0fccfc;
    color: #202733;
  }
  main {
    max-width: 1100px;
    margin: 30px auto 60px;
    padding: 0 20px;
  }
  .dashboard {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 40px 45px;
    max-width: 930px;
    margin: 40px auto 0 auto;
  }
  .folder-card, .service-card, .category-card {
    background: #23273b;
    border: 3px solid #ffe27f;
    border-radius: 18px;
    padding: 46px 30px;
    font-size: 1.3em;
    font-weight: 700;
    color: #ffe27f;
    cursor: pointer;
    user-select: none;
    transition: all 0.3s ease;
    text-align: center;
    box-shadow: 0 0 22px 6px #ffe27fab, 0 7px 42px #102733d8;
    min-width: 240px;
  }
  .folder-card:hover, .service-card:hover, .category-card:hover {
    background: #ffe27f;
    color: #222a39;
    border-color: #0fccfc;
    box-shadow: 0 0 42px 15px #0fccfcbb, 0 7px 42px #23536fab;
    font-weight: 900;
    transform: scale(1.07);
  }
  .section-title {
    font-weight: 700;
    font-size: 1.9rem;
    text-align: center;
    color: #ffe27f;
    margin-bottom: 36px;
    letter-spacing: 1.2px;
    text-shadow: 0 0 24px #ffe27fac;
  }
  .service-list, .events-categories {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(210px,1fr));
    gap: 28px 34px;
    justify-content: center;
    margin: 22px 0 40px 0;
  }
  form.contact-form {
    max-width: 480px;
    margin: 20px auto 60px;
    padding: 36px 40px;
    background: #172440;
    border-radius: 18px;
    border: 2px solid #00e1ff99;
    font-size: 1.12em;
    color: #afdfff;
  }
  form.contact-form label {
    display: block;
    margin-bottom: 10px;
    font-weight: 700;
    color: #8ec7ff;
  }
  form.contact-form input,
  form.contact-form textarea,
  form.contact-form select {
    width: 100%;
    padding: 15px 20px;
    font-size: 16px;
    margin-bottom: 26px;
    border-radius: 10px;
    border: 1.8px solid #38abf7;
    background: #0f1f3a;
    color: #cde4ff;
    box-sizing: border-box;
    resize: vertical;
    outline: none;
    transition: background-color 0.3s ease, border-color 0.3s ease;
  }
  form.contact-form input:focus,
  form.contact-form textarea:focus,
  form.contact-form select:focus {
    background-color: #1a4490;
    border-color: #00bfff;
  }
  form.contact-form button {
    width: 100%;
    padding: 20px 0;
    font-weight: 900;
    font-size: 1.3em;
    color: #192b3a;
    background-color: #00e1ff;
    border: none;
    border-radius: 15px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  form.contact-form button:hover {
    background-color: #3de1ff;
  }
  .back-btn {
    display: block;
    margin: 35px auto 20px;
    padding: 22px 72px;
    font-weight: 900;
    font-size: 1.25em;
    border-radius: 18px;
    background-color: #ffe27f;
    border: 3px solid #ffe27f;
    color: #202733;
    cursor: pointer;
    user-select: none;
    text-align: center;
    width: max-content;
    box-shadow: 0 0 40px 14px #ffe27f88;
    transition: all 0.3s ease;
  }
  .back-btn:hover {
    background-color: #00e1ff;
    color: #fff;
    border-color: #00e1ff;
    box-shadow: 0 0 42px 18px #00e1ffcc;
  }
  video#video {
    max-width: 100%;
    border-radius: 15px;
    border: 2px solid #00e1ff8f;
    margin-top: 28px;
  }
  #map {
    max-width: 640px;
    height: 460px;
    margin: 28px auto 56px;
    border-radius: 15px;
    border: 3px solid #00e1ff94;
    box-shadow: 0 0 36px 18px #00e1ff52;
  }
  #photoOutput img {
    max-width: 320px;
    border-radius: 16px;
  }
  @media(max-width: 900px) {
    .dashboard,
    .service-list,
    .events-categories {
      grid-template-columns: 1fr;
      gap: 26px;
    }
    .folder-card, 
    .service-card, 
    .category-card {
      width: 95%;
      font-size: 1.25rem;
      padding: 38px 22px;
    }
  }
</style>
</head>
<body>
<header>JKS Group of Business</header>
<nav>
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
  <button onclick="showPage('recharge')">Recharge & Bills</button>
</nav>
<main>
<section id="dashboard" class="dashboard"></section>
<section id="profile" style="display:none;">
  <h2 class="section-title">Profile</h2>
  <form class="contact-form" onsubmit="return false;">
    <label>Name:</label>
    <input id="profileName" type="text" />
    <label>Email:</label>
    <input id="profileEmail" type="email" />
    <label>Phone:</label>
    <input id="profilePhone" type="tel" />
    <label>Address:</label>
    <textarea id="profileAddress" rows="3"></textarea>
    <button type="button" onclick="alert('Profile saved!')">Save</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="wallet" style="display:none;">
  <h2 class="section-title">Wallet</h2>
  <p>Balance: ₹<span id="walletBalance">10000</span></p>
  <form class="contact-form" onsubmit="addMoney(event)">
    <label>Add Money:</label>
    <input id="addMoneyInput" type="number" min="1" required/>
    <button type="submit">Add Funds</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="orders" style="display:none;">
  <h2 class="section-title">Orders</h2>
  <table style="width:100%;border-collapse:collapse;background:#1c2238;color:#fff;border-radius:8px;overflow:hidden;">
    <thead><tr><th style="padding:14px;">Order ID</th><th>Product / Service</th><th>Status</th></tr></thead>
    <tbody>
      <tr><td>001</td><td>Pizza</td><td style="color:#3eff9d;">Delivered</td></tr>
      <tr><td>002</td><td>Car Wash</td><td style="color:#ffe27f;">Pending</td></tr>
      <tr><td>003</td><td>Loan Enquiry</td><td style="color:#0bcfff;">In Progress</td></tr>
    </tbody>
  </table>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="serviceView" style="display:none;flex-direction:column;align-items:center;">
  <h2 class="section-title" id="serviceTitle"></h2>
  <div class="service-list" id="serviceList"></div>
  <form class="contact-form" id="contactForm" style="display:none;">
    <label>Name:</label>
    <input id="userName" type="text" required/>
    <label>Mobile:</label>
    <input id="userPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
    <label>Message:</label>
    <textarea id="userMessage" rows="4" required></textarea>
    <button type="button" onclick="submitWhatsApp()">Send WhatsApp</button>
    <button class="back-btn" onclick="backToServiceList()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="events" style="display:none;flex-direction:column;align-items:center;">
  <h2 class="section-title" id="eventsCategoryTitle"></h2>
  <div class="events-categories" id="eventsCategories"></div>
  <div class="service-list" id="eventsServiceList"></div>
  <form id="eventContactForm" class="contact-form" style="display:none;">
    <label>Name:</label>
    <input id="eventsUserName" type="text" required/>
    <label>Mobile:</label>
    <input id="eventsUserPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
    <div id="customFields"></div>
    <label>Message:</label>
    <textarea id="eventsUserMessage" rows="4" required></textarea>
    <button type="button" onclick="submitEventsForm()">Send WhatsApp</button>
    <button class="back-btn" onclick="backToEventsCategory()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="ecommerce" style="display:none;flex-direction:column;align-items:center;">
  <h2 class="section-title">My E-commerce</h2>
  <nav style="margin-bottom:18px;">
    <button onclick="openEcomCategory('Groceries')">Groceries</button>
    <button onclick="openEcomCategory('Food')">Food</button>
    <button onclick="openEcomCategory('Pharmacy')">Pharmacy</button>
  </nav>
  <div class="service-list" id="ecomServiceList"></div>
  <form id="ecomOrderForm" class="contact-form" style="display:none;">
    <h3 id="ecomOrderTitle"></h3>
    <label>Name:</label>
    <input name="name" type="text" required/>
    <label>Mobile:</label>
    <input name="phone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required/>
    <label>Order Details:</label>
    <textarea name="orderDetails" rows="3" required></textarea>
    <label>Delivery Address:</label>
    <textarea name="address" required></textarea>
    <button type="submit">Order WhatsApp</button>
    <button type="button" class="back-btn" onclick="backToEcomServices()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="recharge" style="display:none;flex-direction:column;align-items:center;">
  <h2 class="section-title">Recharge & Pay Bills</h2>
  <div class="service-list" id="rechargeServiceList"></div>
  <form id="rechargeOrderForm" class="contact-form" style="display:none;">
    <h3 id="rechargeOrderTitle"></h3>
    <label>Name:</label>
    <input name="rname" type="text" required/>
    <label>Mobile:</label>
    <input name="rphone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required/>
    <label>Order Details:</label>
    <textarea name="rdetails" rows="3" required></textarea>
    <label>Delivery Address (Optional):</label>
    <textarea name="raddress"></textarea>
    <button type="submit">Order WhatsApp</button>
    <button type="button" class="back-btn" onclick="backToRecharge()">Back</button>
  </form>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="camera" style="display:none;text-align:center;">
  <h2 class="section-title">Camera</h2>
  <video id="video" autoplay muted playsinline></video>
  <div style="margin:20px 0;">
    <button onclick="switchCamera()">Switch Camera</button>
    <button onclick="capturePhoto()">Capture Photo</button>
  </div>
  <canvas id="canvas"></canvas>
  <div id="photoOutput"></div>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
<section id="maps" style="display:none;text-align:center;">
  <h2 class="section-title">Google Maps</h2>
  <iframe id="map" width="100%" height="460" style="border:0; border-radius:14px; margin:28px auto 52px; box-shadow:0 0 36px 18px #00e1ff52;"
          loading="lazy" allowfullscreen referrerpolicy="no-referrer-when-downgrade"
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3806.272668041566!2d78.48261611487654!3d17.385044788065196!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bcb9736285f645f%3A0xf4dae048bfe79116!2sHyderabad!5e0!3m2!1sen!2sin!4v1633072783551!5m2!1sen!2sin"></iframe>
  <button class="back-btn" onclick="showPage('dashboard')">Back</button>
</section>
</main>

<script>
const folders=[
  {id:'ecommerce',label:'My E-commerce'},
  {id:'events',label:'Events & Catering'},
  {id:'courier',label:'Courier & Ride Booking'},
  {id:'job',label:'Job Consultancy & Services'},
  {id:'tours',label:'Tours & Travels'},
  {id:'realestate',label:'Real Estate & Construction'},
  {id:'investment',label:'Investment & Business'},
  {id:'loans',label:'Loans & Insurance'},
  {id:'home',label:'Home Services'},
  {id:'recharge',label:'Recharge & Pay Bills'}
];
const moduleServices={
  courier:['Courier Booking','Ride Booking','Tracking','Support','Rental Vehicles'],
  job:['Job Search','Post Resume','Local Jobs','Non-Local Jobs','PG & Hostel','Services Marketplace'],
  tours:['Tour Bookings','Custom & Regular Tours','Stay Booking','Vehicle Booking','Train/Bus/Flight Tickets'],
  realestate:['Buy','Sell','Rent','Key Services','Construction','Industry'],
  investment:['Gold','Silver','Real Estate','Business Opportunity','Mutual Funds'],
  loans:['Loan Enquiry','Car Insurance','Bike Insurance','Housing Loans','Personal Loans','Health Insurance'],
  home:['CC Camera Installation','Computer Repair','Car Wash','Mobile Repair','Chef Services','Bouncers','Bike Mechanic','Car Mechanic','Electrician','Painter','Plumber','Driver']
};
const ecom={
  Groceries:['Milk','Meat','Fruits','Vegetables','Flowers','Others'],
  Food:['Biriyani','Tiffins','Ice Cream','Pizza','Burgers','Rolls'],
  Pharmacy:['Medicines','Health Products','Supplements','Care Products']
};
const eventsCategories={
  package:[
    {name:'Silver',amount:'50k - 160k'},
    {name:'Gold',amount:'150k - 300k'},
    {name:'Diamond',amount:'500k - 5M'},
    {name:'Platinum',amount:'500k - 800k'}
  ],
  customized:[
    'Decoration','Catering','Photography & Videography','Anchor & Actors','DJ & Singers','Guest House','Chocolate & Cake','Games & Entertainment','Jewellery','Invitation Cards','Vehicles','Return Gifts','Makeup Artist','Mehandi Artist','Clothing & Accessories'
  ],
  premium:[
    'Decoration','Catering','Photography & Videography','Anchor & Actors','DJ & Singers','Guest House','Chocolate & Cake','Games & Entertainment','Jewellery','Invitation Cards','Vehicles','Return Gifts','Makeup Artist','Mehandi Artist','Clothing & Accessories'
  ]
};
const rechargeServices=['Mobile Recharge','DTH Recharge','Electricity Bill','Water Bill','Gas Bill'];
let currentModule='',currentService='',currentEcomCategory='',currentEventCategory='',currentEventService='',currentRechargeService='';

function showPage(page){
  document.querySelectorAll('main > section').forEach(s=>s.style.display='none');
  document.getElementById(page).style.display='block';
  if(page==='dashboard')renderDashboard();
  if(page==='events')openEvents();
  if(page==='ecommerce')openEcom();
  if(page==='recharge')openRecharge();
  if(page==='camera')startCamera();
}
function renderDashboard(){
  const dash=document.getElementById('dashboard');
  dash.innerHTML='';
  folders.forEach(f=>{
    const div=document.createElement('div');
    div.className='folder-card';
    div.textContent=f.label;
    div.onclick=()=>openModule(f.id);
    dash.appendChild(div);
  });
}
function openModule(mod){
  currentModule=mod;
  currentService='';
  if(mod==='events'){openEvents();return;}
  if(mod==='ecommerce'){openEcom();return;}
  if(mod==='recharge'){openRecharge();return;}
  const servList=document.getElementById('serviceList');
  servList.innerHTML='';
  (moduleServices[mod]||[]).forEach(s=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=s;
    d.onclick=()=>openContactForm(s);
    servList.appendChild(d);
  });
  document.getElementById('serviceTitle').textContent=folders.find(f=>f.id===mod)?.label||'';
  showPage('serviceView');
}
function openContactForm(service){
  currentService=service;
  document.getElementById('serviceList').style.display='none';
  const form=document.getElementById('contactForm');
  form.style.display='block';
  clearInputs(['userName','userPhone','userMessage']);
}
function backToServiceList(){
  document.getElementById('contactForm').style.display='none';
  document.getElementById('serviceList').style.display='grid';
}
function submitWhatsApp(){
  const name=document.getElementById('userName').value.trim();
  const phone=document.getElementById('userPhone').value.trim();
  const msg=document.getElementById('userMessage').value.trim();
  if(!name||!phone||!msg){alert('Please fill all fields');return;}
  const waMsg=`Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentService)}%0AMessage: ${encodeURIComponent(msg)}`;
  window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${waMsg}`, '_blank');
}
function clearInputs(ids){ids.forEach(id=>{const e=document.getElementById(id); if(e)e.value='';});}

function openEvents(){
  currentEventCategory='';
  currentEventService='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('ecommerce').style.display='none';
  document.getElementById('recharge').style.display='none';
  document.getElementById('events').style.display='flex';
  const cats=document.getElementById('eventsCategories');
  cats.innerHTML='';
  ['package','customized','premium'].forEach(cat=>{
    const d=document.createElement('div');
    d.className='category-card';
    d.textContent=cat.charAt(0).toUpperCase()+cat.slice(1);
    d.onclick=()=>openEventsCategory(cat);
    cats.appendChild(d);
  });
  document.getElementById('eventsServiceList').innerHTML='';
  document.getElementById('eventContactForm').style.display='none';
  document.getElementById('eventsCategoryTitle').textContent='Events & Catering Categories';
}
function openEventsCategory(category){
  currentEventCategory=category;
  const svcList=document.getElementById('eventsServiceList');
  document.getElementById('eventContactForm').style.display='none';
  svcList.style.display='grid';
  svcList.innerHTML='';
  if(category=='package'){
    eventsCategories.package.forEach(pkg=>{
      const d=document.createElement('div');
      d.className='service-card';
      d.textContent=`${pkg.name} (${pkg.amount})`;
      d.onclick=()=>openEventContactForm(pkg.name, category);
      svcList.appendChild(d);
    });
  }else{
    eventsCategories[category].forEach(svc=>{
      const d=document.createElement('div');
      d.className='service-card';
      d.textContent=svc;
      d.onclick=()=>openEventContactForm(svc, category);
      svcList.appendChild(d);
    });
  }
  document.getElementById('eventsCategoryTitle').textContent=category.charAt(0).toUpperCase()+category.slice(1)+' Services';
}
function openEventContactForm(service, category){
  currentEventService=service;
  document.getElementById('eventsServiceList').style.display='none';
  const form=document.getElementById('eventContactForm');
  form.style.display='block';
  document.getElementById('eventsContactTitle').textContent='Contact for '+service;
  document.getElementById('eventsUserName').value='';
  document.getElementById('eventsUserPhone').value='';
  document.getElementById('eventsUserMessage').value='';
  const customFields=document.getElementById('customFields');
  if(category=='customized'){
    customFields.innerHTML=`
      <label>Budget:</label>
      <select id="eventsBudget" required>
        <option value="">Select Budget</option>
        <option>10k to 50k</option>
        <option>50k to 1L</option>
        <option>1L to 5L</option>
        <option>5L to 10L</option>
        <option>Above 10L</option>
      </select>
      <label>Capacity:</label>
      <select id="eventsCapacity" required>
        <option value="">Select Capacity</option>
        <option>5-30 people</option>
        <option>30-60 people</option>
        <option>60-90 people</option>
        <option>90-130 people</option>
        <option>Above 130 people</option>
      </select>
    `;
  }else{
    customFields.innerHTML='';
  }
}
function backToEventsCategory(){
  document.getElementById('eventContactForm').style.display='none';
  document.getElementById('eventsServiceList').style.display='grid';
}
function submitEventsForm(){
  const name=document.getElementById('eventsUserName').value.trim();
  const phone=document.getElementById('eventsUserPhone').value.trim();
  const message=document.getElementById('eventsUserMessage').value.trim();
  const budget=document.getElementById('eventsBudget')?.value;
  const capacity=document.getElementById('eventsCapacity')?.value;
  if(!name||!phone||!message){
    alert('Please fill all fields');
    return;
  }
  if(currentEventCategory=='customized' && (!budget || !capacity)){
    alert('Select budget and capacity');
    return;
  }
  let waMsg=`Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentEventService)}%0ACategory: ${encodeURIComponent(currentEventCategory)}%0AMessage: ${encodeURIComponent(message)}`;
  if(budget) waMsg+=`%0ABudget: ${encodeURIComponent(budget)}`;
  if(capacity) waMsg+=`%0ACapacity: ${encodeURIComponent(capacity)}`;
  window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${waMsg}`, '_blank');
}
function openEcom(){
  currentEcomCategory='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('recharge').style.display='none';
  document.getElementById('ecommerce').style.display='flex';
  document.getElementById('ecomServiceList').innerHTML='';
}
function openEcomCategory(cat){
  currentEcomCategory=cat;
  const svcList=document.getElementById('ecomServiceList');
  svcList.innerHTML='';
  (ecom[cat]||[]).forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=svc;
    d.onclick=()=>openEcomOrderForm(cat, svc);
    svcList.appendChild(d);
  });
  document.getElementById('ecomOrderForm').style.display='none';
}
function openEcomOrderForm(cat, svc){
  document.getElementById('ecomOrderForm').style.display='block';
  document.getElementById('ecomOrderTitle').textContent=`Order ${svc} in ${cat}`;
  document.getElementById('ecomOrderForm').onsubmit=function(e){
    e.preventDefault();
    const n=document.querySelector('#ecomOrderForm input[name="name"]').value.trim();
    const p=document.querySelector('#ecomOrderForm input[name="phone"]').value.trim();
    const d=document.querySelector('#ecomOrderForm textarea[name="orderDetails"]').value.trim();
    const a=document.querySelector('#ecomOrderForm textarea[name="address"]').value.trim();
    if(!n||!p||!d||!a){
      alert('Fill all order fields');
      return;
    }
    const msg=`Order: ${encodeURIComponent(svc)}%0AName: ${encodeURIComponent(n)}%0APhone: ${encodeURIComponent(p)}%0ADetails: ${encodeURIComponent(d)}%0AAddress: ${encodeURIComponent(a)}`;
    window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${msg}`,'_blank');
  }
}
function backToEcomServices(){
  document.getElementById('ecomOrderForm').style.display='none';
}
function openRecharge(){
  currentRechargeService='';
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('ecommerce').style.display='none';
  document.getElementById('recharge').style.display='flex';
  document.getElementById('rechargeServiceList').innerHTML='';
  rechargeServices.forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.textContent=svc;
    d.onclick=()=>openRechargeOrderForm(svc);
    document.getElementById('rechargeServiceList').appendChild(d);
  });
  document.getElementById('rechargeOrderForm').style.display='none';
}
function openRechargeOrderForm(svc){
  currentRechargeService=svc;
  document.getElementById('rechargeServiceList').style.display='none';
  const form=document.getElementById('rechargeOrderForm');
  form.style.display='block';
  document.getElementById('rechargeOrderTitle').textContent='Pay ' + svc;
  const inputs=form.querySelectorAll('input,textarea');
  inputs.forEach(i=>i.value='');
  form.onsubmit=function(e){
    e.preventDefault();
    const n=document.getElementById('rname').value.trim();
    const p=document.getElementById('rphone').value.trim();
    const d=document.getElementById('rdetails').value.trim();
    const a=document.getElementById('raddress').value.trim();
    if(!n||!p||!d){
      alert('Fill all required fields');
      return;
    }
    const msg=`Recharge Payment: ${encodeURIComponent(svc)}%0AName: ${encodeURIComponent(n)}%0APhone: ${encodeURIComponent(p)}%0ADetails: ${encodeURIComponent(d)}%0AAddress: ${encodeURIComponent(a)}`;
    window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${msg}`,'_blank');
  }
}
function backToRecharge(){
  document.getElementById('rechargeOrderForm').style.display='none';
  document.getElementById('rechargeServiceList').style.display='grid';
}
let stream=null; let front=true;
function startCamera(){
  if(stream) stream.getTracks().forEach(t=>t.stop());
  navigator.mediaDevices.getUserMedia({video:{facingMode:front?'user':'environment'}})
    .then(s=>{
      stream=s;
      document.getElementById('video').srcObject=stream;
      document.getElementById('video').play();
    }).catch(()=>alert('Camera not available'));
}
function switchCamera(){
  front=!front;
  startCamera();
}
function capturePhoto(){
  const video=document.getElementById('video');
  const canvas=document.getElementById('canvas');
  canvas.width=video.videoWidth;
  canvas.height=video.videoHeight;
  canvas.getContext('2d').drawImage(video,0,0);
  const dataUrl=canvas.toDataURL();
  document.getElementById('photoOutput').innerHTML=`<img src="${dataUrl}" style="max-width:320px; border-radius:12px;"/>`;
}
document.addEventListener('DOMContentLoaded',()=>showPage('dashboard'));
</script>
</body>
</html>
