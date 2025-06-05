# Pendaftaran-santri-baru
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Form Pendaftaran Siswa - Pesantren Islam</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Almarai&display=swap');
  :root {
    --primary-green: #2e7d32;
    --secondary-gold: #cfa45d;
    --bg-color: #f9f9f6;
    --input-bg: #ffffff;
    --input-border: #aacd80;
    --error-color: #d32f2f;
  }
  body {
    font-family: 'Almarai', sans-serif;
    margin: 0;
    background-color: var(--bg-color);
    color: #1b3e1b;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 1rem;
  }
  .container {
    background-color: white;
    max-width: 600px;
    width: 100%;
    padding: 2rem 2.5rem 3rem;
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(46,125,50,0.3);
    position: relative;
  }
  .header {
    text-align: center;
    margin-bottom: 1.5rem;
    border-bottom: 2px solid var(--primary-green);
    padding-bottom: 0.75rem;
    position: relative;
  }
  .header h1 {
    margin: 0;
    font-size: 1.8rem;
    color: var(--primary-green);
    font-weight: 700;
  }
  .header::after {
    content: '';
    position: absolute;
    top: -10px;
    right: 10px;
    width: 60px;
    height: 60px;
    background: radial-gradient(circle at 25% 25%, var(--primary-green), transparent 70%);
    border-radius: 50%;
    box-shadow: -18px 0 0 var(--bg-color);
    transform: rotate(15deg);
    opacity: 0.2;
  }
  form {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem 2rem;
  }
  label {
    display: block;
    font-weight: 600;
    margin-bottom: 0.3rem;
  }
  input[type="text"],
  input[type="email"],
  input[type="tel"],
  input[type="date"],
  select,
  textarea {
    width: 100%;
    padding: 0.5rem 0.75rem;
    border: 2px solid var(--input-border);
    border-radius: 6px;
    background-color: var(--input-bg);
    font-size: 1rem;
    font-family: inherit;
    transition: border-color 0.3s ease;
  }
  input[type="text"]:focus,
  input[type="email"]:focus,
  input[type="tel"]:focus,
  input[type="date"]:focus,
  select:focus,
  textarea:focus {
    border-color: var(--secondary-gold);
    outline: none;
    box-shadow: 0 0 5px var(--secondary-gold);
  }
  textarea {
    resize: vertical;
    min-height: 70px;
  }
  .full-width {
    grid-column: 1 / -1;
  }
  .gender-group {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-top: 0.3rem;
  }
  .gender-group label {
    margin-bottom: 0;
    font-weight: normal;
    cursor: pointer;
    user-select: none;
  }
  input[type="radio"] {
    margin-right: 0.3rem;
    accent-color: var(--primary-green);
  }
  button {
    grid-column: 1 / -1;
    background: linear-gradient(135deg, var(--primary-green), var(--secondary-gold));
    color: white;
    font-weight: 700;
    font-size: 1.1rem;
    padding: 0.75rem;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.4s ease;
  }
  button:hover,
  button:focus {
    background: linear-gradient(135deg, var(--secondary-gold), var(--primary-green));
    outline: none;
  }
  .confirmation {
    margin-top: 1rem;
    background-color: #dff0d8;
    color: #3c763d;
    padding: 1rem;
    border-radius: 8px;
    border: 1px solid #d6e9c6;
    font-weight: 600;
  }
  .error {
    color: var(--error-color);
    font-size: 0.9rem;
    margin-top: 0.2rem;
  }
  @media (max-width: 600px) {
    form {
      grid-template-columns: 1fr;
    }
    .gender-group {
      justify-content: flex-start;
      gap: 1rem;
    }
    .full-width {
      grid-column: 1 / -1;
    }
  }
</style>
</head>
<body>
  <div class="container" role="main">
    <header class="header">
      <h1>Pendaftaran Siswa</h1>
      <p>Pesantren Islam</p>
    </header>
    <form id="registrationForm" novalidate>
      <div class="full-width">
        <label for="fullName">Nama Lengkap *</label>
        <input type="text" id="fullName" name="fullName" required autocomplete="name" placeholder="Masukkan nama lengkap" />
        <div class="error" id="fullNameError"></div>
      </div>
      <div>
        <label for="dob">Tanggal Lahir *</label>
        <input type="date" id="dob" name="dob" required max="" />
        <div class="error" id="dobError"></div>
      </div>
      <div>
        <label>Jenis Kelamin *</label>
        <div class="gender-group" role="radiogroup" aria-labelledby="gender-label">
          <label><input type="radio" name="gender" value="Male" required /> Laki-laki</label>
          <label><input type="radio" name="gender" value="Female" /> Perempuan</label>
          <label><input type="radio" name="gender" value="Other" /> Lainnya</label>
        </div>
        <div class="error" id="genderError"></div>
      </div>
      <div>
        <label for="nationality">Kewarganegaraan *</label>
        <input type="text" id="nationality" name="nationality" required placeholder="mis. Warga Negara Indonesia" />
        <div class="error" id="nationalityError"></div>
      </div>
      <div class="full-width">
        <label for="address">Alamat *</label>
        <textarea id="address" name="address" required placeholder="Masukkan alamat lengkap"></textarea>
        <div class="error" id="addressError"></div>
      </div>
      <div>
        <label for="parentName">Nama Orang Tua/Wali *</label>
        <input type="text" id="parentName" name="parentName" required placeholder="Masukkan nama lengkap wali" />
        <div class="error" id="parentNameError"></div>
      </div>
      <div>
        <label for="contactNumber">Nomor Kontak *</label>
        <input type="tel" id="contactNumber" name="contactNumber" required placeholder="+62 8xxxxxx" />
        <div class="error" id="contactNumberError"></div>
      </div>
      <div>
        <label for="email">Alamat Email</label>
        <input type="email" id="email" name="email" placeholder="contoh@mail.com" />
        <div class="error" id="emailError"></div>
      </div>
      <div>
          <label for="previousSchool">Sekolah Sebelumnya</label>
          <input type="text" id="previousSchool" name="previousSchool" placeholder="Jika ada" />
      </div>
      <div>
        <label for="preferredGrade">Kelas yang Diinginkan *</label>
        <select id="preferredGrade" name="preferredGrade" required>
          <option value="" disabled selected>Pilih kelas</option>
          <option>Kelas 1</option>
          <option>Kelas 2</option>
          <option>Kelas 3</option>
          <option>Kelas 4</option>
          <option>Kelas 5</option>
          <option>Kelas 6</option>
          <option>SMP</option>
          <option>SMA</option>
        </select>
        <div class="error" id="preferredGradeError"></div>
      </div>
      <div>
        <label for="religion">Agama *</label>
        <select id="religion" name="religion" required>
          <option value="" disabled selected>Pilih agama</option>
          <option>Islam - Sunni</option>
          <option>Islam - Shia</option>
          <option>Islam - Lainnya</option>
          <option>Lainnya</option>
          <option>Lebih baik tidak mengatakan</option>
        </select>
        <div class="error" id="religionError"></div>
      </div>
      <div class="full-width">
        <label for="emergencyContact">Nama & Nomor Kontak Darurat *</label>
        <input type="text" id="emergencyContact" name="emergencyContact" required placeholder="Nama dan nomor telepon" />
        <div class="error" id="emergencyContactError"></div>
      </div>
      <div class="full-width">
        <label for="medicalInfo">Kondisi Medis atau Alergi</label>
        <textarea id="medicalInfo" name="medicalInfo" placeholder="Silakan sebutkan jika ada"></textarea>
      </div>
      <div class="full-width">
        <button type="submit" aria-label="Kirim Form Pendaftaran">Daftar</button>
      </div>
    </form>
    <div id="confirmationMessage" class="confirmation" role="alert" style="display:none;"></div>
  </div>

<script>
  document.getElementById('dob').max = new Date().toISOString().split("T")[0];

  const form = document.getElementById('registrationForm');
  const confirmation = document.getElementById('confirmationMessage');

  form.addEventListener('submit', function(event) {
    event.preventDefault();
    clearErrors();
    const isValid = validateForm();
    if(isValid){
      confirmation.textContent = "Terima kasih telah mendaftar! Formulir Anda telah berhasil dikirim.";
      confirmation.style.display = 'block';
      form.reset();
      window.scrollTo({top:0, behavior: 'smooth'});
    }
  });

  function clearErrors() {
    const errors = document.querySelectorAll('.error');
    errors.forEach(error => error.textContent = '');
    confirmation.style.display = 'none';
  }

  function validateForm(){
    let valid = true;
    const fullName = form.fullName.value.trim();
    if(!fullName){
      showError('fullNameError', 'Nama Lengkap diperlukan.');
      valid = false;
    }
    const dob = form.dob.value;
    if(!dob){
      showError('dobError', 'Tanggal Lahir diperlukan.');
      valid = false;
    } else {
      const dobDate = new Date(dob);
      const today = new Date();
      if(dobDate > today){
        showError('dobError', 'Tanggal Lahir tidak boleh di masa depan.');
        valid = false;
      }
    }
    const gender = form.gender.value;
    if(!gender){
      showError('genderError', 'Silakan pilih jenis kelamin.');
      valid = false;
    }
    const nationality = form.nationality.value.trim();
    if(!nationality){
      showError('nationalityError', 'Kewarganegaraan diperlukan.');
      valid = false;
    }
    const address = form.address.value.trim();
    if(!address){
      showError('addressError', 'Alamat diperlukan.');
      valid = false;
    }
    const parentName = form.parentName.value.trim();
    if(!parentName){
      showError('parentNameError', "Nama Orang Tua/Wali diperlukan.");
      valid = false;
    }
    const contactNumber = form.contactNumber.value.trim();
    if(!contactNumber){
      showError('contactNumberError', 'Nomor Kontak diperlukan.');
      valid = false;
    } else {
      const phoneRegex = /^[+]?[\d\s\-]+$/;
      if(!phoneRegex.test(contactNumber)){
        showError('contactNumberError', 'Silakan masukkan nomor kontak yang valid.');
        valid = false;
      }
    }
    const email = form.email.value.trim();
    if(email){
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if(!emailRegex.test(email)){
        showError('emailError', 'Silakan masukkan alamat email yang valid.');
        valid = false;
      }
    }
    const preferredGrade = form.preferredGrade.value;
    if(!preferredGrade){
      showError('preferredGradeError', 'Silakan pilih kelas yang diinginkan.');
      valid = false;
    }
    const religion = form.religion.value;
    if(!religion){
      showError('religionError', 'Silakan pilih agama Anda.');
      valid = false;
    }
    const emergencyContact = form.emergencyContact.value.trim();
    if(!emergencyContact){
      showError('emergencyContactError', 'Informasi kontak darurat diperlukan.');
      valid = false;
    }
    return valid;
  }

  function showError(elementId, message){
    const element = document.getElementById(elementId);
    if(element){
      element.textContent = message;
    }
  }
</script>
</body>
</html>
