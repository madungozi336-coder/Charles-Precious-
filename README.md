index html 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Admissions | Charles Precious School</title>

<style>CharlesPreciousAcademy/
│
├── index.html
└── charles-precious-academy-logo.png<img
    src="charles-precious-academy-logo.png"
    alt="Charles Precious Academy Logo"
    width="180"
:root {
    --blue: #87CEEB;
    --orange: #FF8C42;
    --purple: #7952B3;
    --dark: #20284A;
    --white: #FFFFFF;
}

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #EAF8FF, #F5EEFF);
    color: var(--dark);
    line-height: 1.6;
}

header {
    background: var(--white);
    padding: 22px 15px;
    text-align: center;
    border-bottom: 5px solid var(--blue);
}

.logo {
    font-size: 25px;
    font-weight: bold;
    color: var(--purple);
}

header p {
    margin-bottom: 0;
}

.container {
    max-width: 760px;
    margin: 35px auto;
    padding: 30px;
    background: var(--white);
    border-radius: 20px;
    box-shadow: 0 8px 30px #20284A15;
}

h1 {
    text-align: center;
    color: var(--purple);
    margin-bottom: 8px;
}

.intro {
    text-align: center;
    margin-bottom: 30px;
}

h2 {
    color: var(--purple);
    font-size: 19px;
    border-bottom: 2px solid var(--blue);
    padding-bottom: 8px;
    margin-top: 30px;
}

label {
    display: block;
    margin: 15px 0 6px;
    font-weight: bold;
}

input, select, textarea {
    width: 100%;
    padding: 13px;
    border: 1px solid #CCD4E5;
    border-radius: 9px;
    font-size: 16px;
    background: #FCFDFF;
}

input:focus, select:focus, textarea:focus {
    outline: 2px solid var(--blue);
    border-color: var(--purple);
}

textarea {
    min-height: 90px;
    resize: vertical;
}

button {
    width: 100%;
    margin-top: 25px;
    padding: 15px;
    border: none;
    border-radius: 10px;
    background: var(--orange);
    color: white;
    font-size: 17px;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    background: var(--purple);
}

.note {
    margin-top: 18px;
    font-size: 13px;
    color: #59627A;
}

#result {
    display: none;
    margin-top: 20px;
    padding: 15px;
    border-radius: 10px;
    background: #E8F7EE;
    color: #14532D;
    overflow-wrap: anywhere;
}

footer {
    text-align: center;
    padding: 20px;
    color: #59627A;
}

@media (max-width: 600px) {
    .container {
        margin: 18px 12px;
        padding: 20px;
    }

    .logo {
        font-size: 21px;
    }
}
</style>
</head>

<body>

<header>
    <div class="logo">✦ CHARLES PRECIOUS SCHOOL</div>
    <p>Where Every Child Discovers Their Brilliance.</p>
</header>

<main class="container">

    <h1>Admission Application</h1>

    <p class="intro">
        We welcome your interest in Charles Precious School.
        Please complete the form below.
    </p>

    <form id="admissionForm">

        <h2>1. Student Information</h2>

        <label for="studentName">Student's Full Name *</label>
        <input id="studentName" name="studentName"
               type="text" required>

        <label for="dob">Date of Birth *</label>
        <input id="dob" name="dob"
               type="date" required>

        <label for="gender">Gender *</label>
        <select id="gender" name="gender" required>
            <option value="">Select gender</option>
            <option>Male</option>
            <option>Female</option>
            <option>Prefer not to say</option>
        </select>

        <label for="level">School Level *</label>
        <select id="level" name="level" required>
            <option value="">Choose school level</option>
            <option>Elementary</option>
            <option>Primary</option>
            <option>Secondary</option>
        </select>

        <label for="className">Class Applying For *</label>
        <input id="className" name="className"
               type="text"
               placeholder="e.g. Primary 3 or JSS 1"
               required>

        <label for="previousSchool">Previous School</label>
        <input id="previousSchool" name="previousSchool"
               type="text">

        <h2>2. Parent or Guardian Information</h2>

        <label for="parentName">Parent/Guardian's Full Name *</label>
        <input id="parentName" name="parentName"
               type="text" required>

        <label for="phone">Phone Number *</label>
        <input id="phone" name="phone"
               type="tel"
               placeholder="Enter contact number"
               required>

        <label for="email">Email Address</label>
        <input id="email" name="email"
               type="email">

        <label for="address">Home Address *</label>
        <textarea id="address" name="address"
                  required></textarea>

        <label for="emergency">Alternative Emergency Contact</label>
        <input id="emergency" name="emergency"
               type="tel">

        <h2>3. Additional Information</h2>

        <label for="notes">Additional Information</label>
        <textarea id="notes" name="notes"
                  placeholder="Anything the school should know?"></textarea>

        <button type="submit">
            Prepare Admission Application
        </button>

        <p class="note">
            Fields marked * are required. Please check all
            details before submitting.
        </p>

    </form>

    <div id="result" role="status" aria-live="polite"></div>

</main>

<footer>
    <p><strong>Charles Precious School</strong></p>
    <p>Prestige, No. 11 Samuel Street</p>
    <p>© <span id="year"></span> Charles Precious School</p>
</footer>

<script>
document.getElementById("year").textContent =
    new Date().getFullYear();

document.getElementById("admissionForm")
.addEventListener("submit", function(event) {

    event.preventDefault();

    const student = document
        .getElementById("studentName").value.trim();

    const parent = document
        .getElementById("parentName").value.trim();

    const level = document
        .getElementById("level").value;

    const result = document
        .getElementById("result");

    result.style.display = "block";

    result.textContent =
        "Thank you, " + parent +
        ". Your application details for " + student +
        " (" + level + ") have been checked in this browser. " +
        "This is a demonstration only: the application has NOT " +
        "been sent to the school. Please contact the school " +
        "to complete the admission process.";
});
</script>

</body>
</html>
