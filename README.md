
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Smart Hostel Complaint Management System</title>

<style>
/* ===== BLUE THEME ===== */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f1f5ff;
    color: #1e293b;
}

header {
    background: #9badea;
    color: white;
    padding: 20px;
    text-align: center;
}

nav {
    background: #3b82f6;
    display: flex;
    justify-content: center;
    gap: 20px;
    padding: 10px;
}

nav button {
    background: #e0e7ff;
    border: none;
    padding: 8px 15px;
    border-radius: 5px;
    cursor: pointer;
    color: #404c74;
}

nav button:hover {
    background: #c7d2fe;
}

section {
    display: none;
    padding: 30px;
}

.active {
    display: block;
}

.card {
    background: white;
    max-width: 500px;
    margin: auto;
    padding: 25px;
    border-radius: 10px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

input, select, textarea {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
}

button.main {
    width: 100%;
    padding: 10px;
    background: #446bec;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
}

th, td {
    border: 1px solid #c7d2fe;
    padding: 8px;
    text-align: center;
}

th {
    background: #e0e7ff;
}

img {
    width: 100%;
    border-radius: 10px;
    margin-bottom: 15px;
}
</style>
</head>

<body>

<header>
    <h1>Smart Hostel Complaint Management System</h1>
    <p>Fast • Transparent • Digital</p>
</header>

<nav>
    <button onclick="showPage('home')">Home</button>
    <button onclick="showPage('complaint')">Register Complaint</button>
    <button onclick="showPage('status')">Track Status</button>
</nav>

<!-- ===== HOME ===== -->
<section id="home" class="active">
    <div class="card">
        <img src="data:image/svg+xml;utf8,
        <svg xmlns='http://www.w3.org/2000/svg' width='400' height='200'>
        <rect width='100%' height='100%' fill='%233b82f6'/>
        <text x='50%' y='50%' fill='white' font-size='24' text-anchor='middle' dominant-baseline='middle'>
        Hostel Complaint Portal
        </text></svg>">

        <h3>About the System</h3>
        <p>
            This system allows hostel students to register complaints related
            to maintenance, cleanliness, electricity, water, or security.
            Students can track complaint status online for transparency and
            faster resolution.
        </p>
    </div>
</section>

<!-- ===== REGISTER COMPLAINT ===== -->
<section id="complaint">
    <div class="card">
        <img src="data:image/svg+xml;utf8,
        <svg xmlns='http://www.w3.org/2000/svg' width='400' height='200'>
        <rect width='100%' height='100%' fill='%231e40af'/>
        <text x='50%' y='50%' fill='white' font-size='22' text-anchor='middle' dominant-baseline='middle'>
        Register Complaint
        </text></svg>">

        <h3>Submit Complaint</h3>
        <input id="studentName" type="text" placeholder="Student Name">
        <select id="category">
            <option>Maintenance</option>
            <option>Cleanliness</option>
            <option>Security</option>
            <option>Electricity</option>
        </select>
        <textarea id="description" placeholder="Complaint Description"></textarea>
        <button class="main" onclick="addComplaint()">Submit</button>
    </div>
</section>

<!-- ===== STATUS ===== -->
<section id="status">
    <div class="card">
        <img src="data:image/svg+xml;utf8,
        <svg xmlns='http://www.w3.org/2000/svg' width='400' height='200'>
        <rect width='100%' height='100%' fill='%236366f1'/>
        <text x='50%' y='50%' fill='white' font-size='22' text-anchor='middle' dominant-baseline='middle'>
        Complaint Status
        </text></svg>">

        <h3>Track Complaints</h3>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Category</th>
                    <th>Status</th>
                </tr>
            </thead>
            <tbody id="complaintList"></tbody>
        </table>
    </div>
</section>

<script>
let complaints = [];

function showPage(page) {
    document.querySelectorAll("section").forEach(sec => sec.classList.remove("active"));
    document.getElementById(page).classList.add("active");
}

function addComplaint() {
    let name = document.getElementById("studentName").value;
    let category = document.getElementById("category").value;

    if (name === "") return;

    complaints.push({ name, category, status: "Pending" });

    let row = `<tr>
        <td>${name}</td>
        <td>${category}</td>
        <td>Pending</td>
    </tr>`;

    document.getElementById("complaintList").innerHTML += row;

    alert("Complaint Submitted Successfully!");
}
</script>

</body>
</html>
