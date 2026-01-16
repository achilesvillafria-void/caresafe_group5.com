<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Care Safe</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"> <!-- For icons -->

<style>
:root {
  --primary: #d32f2f;
  --secondary: #b71c1c;
  --accent: #ffebee;
  --text: #333;
  --light: #f9f9f9;
  --shadow: rgba(0,0,0,0.1);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, var(--light) 0%, #ffffff 100%);
  color: var(--text);
  line-height: 1.6;
}

/* HEADER */
header {
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  color: white;
  padding: 40px 20px;
  text-align: center;
  box-shadow: 0 4px 8px var(--shadow);
  position: relative;
  overflow: hidden;
}
header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80') no-repeat center center;
  background-size: cover;
  opacity: 0.3;
  z-index: 1;
}
header h1, header p {
  position: relative;
  z-index: 2;
}
header h1 {
  font-size: clamp(2rem, 5vw, 3rem);
  font-weight: 700;
  margin-bottom: 10px;
}
header p {
  font-size: clamp(1rem, 3vw, 1.2rem);
  opacity: 0.9;
}

/* NAV */
nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  background: var(--secondary);
  box-shadow: 0 2px 4px var(--shadow);
}
nav button {
  flex: 1 1 auto;
  min-width: 140px;
  background: none;
  border: none;
  color: white;
  padding: 15px 20px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
}
nav button:hover {
  background: rgba(255,255,255,0.1);
}
nav button.active {
  background: white;
  color: var(--secondary);
  font-weight: bold;
}
nav button.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 50%;
  height: 3px;
  background: var(--primary);
}

/* PAGE CONTENT */
.page {
  display: none;
  padding: 40px 20px;
  max-width: 1200px;
  margin: 0 auto;
}
.page.active { display: block; }

h2 {
  color: var(--primary);
  border-bottom: 4px solid var(--primary);
  padding-bottom: 10px;
  font-size: clamp(1.6rem, 4vw, 2.2rem);
  margin-bottom: 20px;
}
h3 {
  color: var(--secondary);
  font-size: 1.4rem;
  margin-top: 20px;
  margin-bottom: 10px;
}
ul {
  line-height: 1.8;
  padding-left: 20px;
  font-size: 1rem;
}
li {
  margin-bottom: 8px;
}

/* CARDS */
.card {
  background: white;
  border-left: 6px solid var(--primary);
  padding: 20px;
  margin: 20px 0;
  border-radius: 8px;
  box-shadow: 0 4px 12px var(--shadow);
  transition: transform 0.3s ease;
}
.card:hover {
  transform: translateY(-5px);
}
.card strong {
  color: var(--secondary);
  font-size: 1.1rem;
}

/* HOTLINES */
.hotline {
  background: var(--accent);
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 8px;
  font-size: 1rem;
  border-left: 4px solid var(--primary);
}

/* MAP */
.map-container {
  margin: 30px 0;
  width: 100%;
  height: 450px;
  border: 2px solid var(--primary);
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px var(--shadow);
}

/* FOOTER */
footer {
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  color: white;
  text-align: center;
  padding: 30px 20px;
  font-size: 1rem;
  line-height: 1.5;
  box-shadow: 0 -4px 8px var(--shadow);
}

/* RESPONSIVE */
@media (max-width: 768px) {
  nav button {
    flex: 1 1 45%;
    font-size: 0.9rem;
    padding: 12px 15px;
  }
  ul { font-size: 0.95rem; }
  .map-container { height: 350px; }
  .card { padding: 15px; }
}
@media (max-width: 480px) {
  nav { flex-direction: column; }
  nav button {
    width: 100%;
    border-bottom: 1px solid rgba(255,255,255,0.2);
    padding: 15px;
  }
  .page { padding: 20px 15px; }
  .map-container { height: 300px; }
  header { padding: 30px 15px; }
}

/* HOME PAGE ENHANCEMENTS */
.hero {
  text-align: center;
  margin-bottom: 30px;
}
.hero p {
  font-size: 1.1rem;
  margin: 20px 0;
}
.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 30px;
}
.feature {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 12px var(--shadow);
  text-align: center;
  transition: transform 0.3s ease;
}
.feature:hover {
  transform: translateY(-5px);
}
.feature i {
  font-size: 2rem;
  color: var(--primary);
  margin-bottom: 10px;
}
</style>
</head>
<body>

<header>
  <h1><i class="fas fa-shield-alt"></i> CARE SAFE</h1>
  <p>Your Disaster Preparedness & Safety Guide</p>
</header>

<nav>
  <button type="button" data-page="home" class="active"><i class="fas fa-home"></i> Home</button>
  <button type="button" data-page="flood"><i class="fas fa-water"></i> Flood</button>
  <button type="button" data-page="typhoon"><i class="fas fa-wind"></i> Typhoon</button>
  <button type="button" data-page="earthquake"><i class="fas fa-house-damage"></i> Earthquake</button>
  <button type="button" data-page="gobag"><i class="fas fa-suitcase"></i> Emergency Go Bag</button>
  <button type="button" data-page="hotlines"><i class="fas fa-phone"></i> Hotlines & Hospitals</button>
</nav>

<!-- HOME -->
<div id="home" class="page active">
  <div class="hero">
    <h2>Welcome to Care Safe</h2>
    <p>Empowering communities with knowledge to stay safe during disasters. Get prepared with our comprehensive guides on floods, typhoons, earthquakes, and more.</p>
  </div>
  <div class="card">
    <strong>CareSafe</strong> is a disaster preparedness website that provides simple guides on what to do 
    <strong>before, during, and after</strong> major natural hazards such as 
    <strong>earthquakes, floods, and typhoons</strong>.<br><br>
    It helps people stay safe, reduce risks, and be ready for emergencies by offering clear action steps, safety tips, and trusted information. Additionally, remember to stay informed through local authorities and have a family communication plan in place.
  </div>
  <div class="features">
    <div class="feature">
      <i class="fas fa-book-open"></i>
      <h3>Easy Guides</h3>
      <p>Simple, step-by-step instructions for every disaster scenario.</p>
    </div>
    <div class="feature">
      <i class="fas fa-clock"></i>
      <h3>Before, During, After</h3>
      <p>Comprehensive plans for all phases of an emergency.</p>
    </div>
    <div class="feature">
      <i class="fas fa-suitcase-rolling"></i>
      <h3>Go Bag Checklist</h3>
      <p>Essential items to pack for quick evacuation.</p>
    </div>
    <div class="feature">
      <i class="fas fa-phone-alt"></i>
      <h3>Hotlines & Maps</h3>
      <p>Direct access to emergency contacts and hospital locations.</p>
    </div>
    <div class="feature">
      <i class="fas fa-mobile-alt"></i>
      <h3>Mobile Friendly</h3>
      <p>Accessible on all devices for on-the-go safety info.</p>
    </div>
  </div>
</div>

<!-- FLOOD -->
<div id="flood" class="page">
  <h2><i class="fas fa-water"></i> Flood Safety</h2>
  <div class="card">
    <strong>BEFORE:</strong>
    <ul>
      <li>Prepare an emergency kit and family plan</li>
      <li>Avoid flood-prone areas</li>
      <li>Elevate electrical systems</li>
      <li>Clear drains and canals</li>
      <li>Know evacuation routes</li>
      <li>Install sandbags if needed</li>
    </ul>
  </div>
  <div class="card">
    <strong>DURING:</strong>
    <ul>
      <li>Move to higher ground</li>
      <li>Avoid floodwaters</li>
      <li>Turn off electricity if safe</li>
      <li>Stay updated through radio or TV</li>
      <li>Do not drive through flooded areas</li>
    </ul>
  </div>
  <div class="card">
    <strong>AFTER:</strong>
    <ul>
      <li>Return only when safe</li>
      <li>Avoid contaminated water</li>
      <li>Document damages</li>
      <li>Seek medical help for injuries</li>
    </ul>
  </div>
</div>

<!-- TYPHOON -->
<div id="typhoon" class="page">
  <h2><i class="fas fa-wind"></i> Typhoon Safety</h2>
  <div class="card">
    <strong>BEFORE:</strong>
    <ul>
      <li>Prepare supplies</li>
      <li>Secure your home</li>
      <li>Charge devices</li>
      <li>Stock up on essentials</li>
    </ul>
  </div>
  <div class="card">
    <strong>DURING:</strong>
    <ul>
      <li>Stay indoors</li>
      <li>Keep updated</li>
      <li>Avoid windows</li>
    </ul>
  </div>
  <div class="card">
    <strong>AFTER:</strong>
    <ul>
      <li>Check for injuries</li>
      <li>Inspect home damages</li>
      <li>Follow official announcements</li>
      <li>Be cautious of downed power lines</li>
    </ul>
  </div>
</div>

<!-- EARTHQUAKE -->
<div id="earthquake" class="page">
  <h2><i class="fas fa-house-damage"></i> Earthquake Safety</h2>
  <div class="card">
    <strong>BEFORE:</strong>
    <ul>
      <li>Secure furniture</li>
      <li>Prepare emergency kit</li>
      <li>Identify safe spots</li>
    </ul>
  </div>
  <div class="card">
    <strong>DURING:</strong>
    <ul>
      <li>Duck, Cover, and Hold</li>
      <li>Stay calm</li>
      <li>Stay away from windows</li>
    </ul>
  </div>
  <div class="card">
    <strong>AFTER:</strong>
    <ul>
      <li>Check injuries</li>
      <li>Expect aftershocks</li>
      <li>Evacuate if building is unsafe</li>
    </ul>
  </div>
</div>

<!-- GO BAG -->
<div id="gobag" class="page">
  <h2><i class="fas fa-suitcase"></i> Emergency Go Bag</h2>
  <div class="card">
    <p>Prepare a go bag with essentials for quick evacuation. Include:</p>
    <ul>
      <li>Water and non-perishable food (for 3 days)</li>
      <li>Flashlight and extra batteries</li>
      <li>First aid kit with medications</li>
      <li>Important documents (ID, insurance)</li>
      <li>Clothes, blankets, and hygiene items</li>
      <li>Cash, phone charger, and whistle</li>
      <li>Multi-tool and duct tape</li>
    </ul>
  </div>
</div>

<!-- HOTLINES & MAP -->
<div id="hotlines" class="page">
  <h2><i class="fas fa-phone"></i> Hotlines & Hospitals</h2>

  <h3>Emergency Hotlines</h3>
  <div class="hotline"><strong>ZCDRRMO:</strong> 995-9601 | 990-1171</div>
  <div class="hotline"><strong>Emergency Operations:</strong> 0966-731-6242</div>
  <div class="hotline"><strong>Fire District:</strong> 991-2267</div>

  <h3>Hospitals</h3>
  <ul>
    <li>Zamboanga City Medical Center</li>
    <li>West Metro Medical Center</li>
    <li>Zamboanga Doctor’s Hospital</li>
    <li>Brent Hospital</li>
    <li>Additional: Mindanao Central Sanitarium</li>
  </ul>

  <div class="map-container">
    <iframe src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d63367.80657114725!2d122.06668914477956!3d6.951628366602374!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1sZamboanga%20city%20all%20hospital!5e0!3m2!1sen!2sph!4v1768486241986!5m2!1sen!2sph" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
  </div>
</div>

<footer>
  <p>Through Care Safe, we aim to keep communities <strong>informed, prepared, and safe when disasters strike</strong>.</p>
  <p>&copy; 2023 Care Safe. All rights reserved.</p>
</footer>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const buttons = document.querySelectorAll("nav button");
  const pages = document.querySelectorAll(".page");

  function showPage(pageId) {
    pages.forEach(page => page.classList.remove("active"));
    document.getElementById(pageId).classList.add("active");

    buttons.forEach(b => b.classList.remove("active"));
    document.querySelector(`nav button[data-page="${pageId}"]`).classList.add("active");
  }

  buttons.forEach(btn => {
    btn.addEventListener("click", () => showPage(btn.dataset.page));
  });
});
</script>

</body>
</html>
```
