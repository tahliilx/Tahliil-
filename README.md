# Tahliil-
Xoosh<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Book an Appointment</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background: #f9f9f9;
      display: flex;
      justify-content: center;
      min-height: 100vh;
      align-items: center;
      margin: 0;
      flex-direction: column;
    }
    form {
      background: white;
      padding: 25px;
      border-radius: 8px;
      box-shadow: 0 0 10px #ccc;
      max-width: 400px;
      width: 100%;
      box-sizing: border-box;
    }
    h2 {
      margin-top: 0;
      text-align: center;
      color: #333;
    }
    label {
      display: block;
      margin-top: 15px;
      color: #333;
      font-weight: 600;
    }
    input, select, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 6px;
      border-radius: 4px;
      border: 1px solid #ccc;
      box-sizing: border-box;
      font-size: 1em;
      resize: vertical;
    }
    button {
      margin-top: 20px;
      width: 100%;
      padding: 12px;
      background-color: #007BFF;
      border: none;
      color: white;
      font-size: 1.1em;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }
    button:hover {
      background-color: #0056b3;
    }
    .success-message {
      margin-top: 15px;
      padding: 15px;
      background-color: #d4edda;
      border: 1px solid #c3e6cb;
      color: #155724;
      border-radius: 5px;
      display: none;
      text-align: center;
      font-weight: 600;
    }
    .contact-number {
      margin-top: 20px;
      font-size: 1.1em;
      color: #444;
      font-weight: 600;
    }
  </style>
</head>
<body>

  <form id="booking-form" action="https://formspree.io/f/xldnlbak" method="POST">
    <h2>Book an Appointment</h2>

    <label for="name">Full Name *</label>
    <input type="text" id="name" name="name" required />

    <label for="email">Email *</label>
    <input type="email" id="email" name="email" required />

    <label for="phone">Phone Number</label>
    <input type="tel" id="phone" name="phone" />

    <label for="date">Preferred Date *</label>
    <input type="date" id="date" name="date" required />

    <label for="time">Preferred Time *</label>
    <input type="time" id="time" name="time" required />

    <label for="service">Service *</label>
    <select id="service" name="service" required>
      <option value="" disabled selected>Select a service</option>
      <option value="Consultation">Consultation</option>
      <option value="Follow-up">Follow-up</option>
      <option value="Emergency">Emergency</option>
    </select>

    <label for="notes">Additional Notes</label>
    <textarea id="notes" name="message" rows="4" placeholder="Any details or requests..."></textarea>

    <button type="submit">Book Now</button>

    <div class="success-message" id="success-message">
      Thank you! Your appointment has been booked.
    </div>
  </form>

  <div class="contact-number">
    📞 Contact us: 8327612
  </div>

  <script>
    const form = document.getElementById('booking-form');
    const successMessage = document.getElementById('success-message');

    form.addEventListener('submit', async (e) => {
      e.preventDefault();

      const formData = new FormData(form);
      const response = await fetch(form.action, {
        method: form.method,
        body: formData,
        headers: { 'Accept': 'application/json' }
      });

      if (response.ok) {
        form.reset();
        successMessage.style.display = 'block';
      } else {
        alert('Oops! There was a problem submitting your form.');
      }
    });
  </script>

</body>
</html>
