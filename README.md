index html 
<!DOCTYPE html>



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
