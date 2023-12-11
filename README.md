<!-- Assume you have a form that collects appointment information -->
<form id="appointmentForm">
  <!-- Your form fields go here -->
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="date">Date:</label>
  <input type="date" id="date" name="date" required>

  <button type="button" onclick="submitAppointment()">Submit Appointment</button>
</form>

<script src="https://cdnjs.cloudflare.com/ajax/libs/axios/0.19.2/axios.min.js"></script>
<script>
  function submitAppointment() {
    // Get form data
    const name = document.getElementById('name').value;
    const date = document.getElementById('date').value;

    // Create an object with the form data
    const appointmentData = {
      name: name,
      date: date,
    };

    // Make a POST request using Axios
    axios.post('https://crudcrud.com/api/8e23919fd76846508df8dd15c3e59333/appointments', appointmentData)
      .then(response => {
        console.log('POST Request Successful:', response.data);
        // Check Crud Crud resource for the data: https://crudcrud.com/api/YOUR_CRUDCRUD_API_KEY/appointments
      })
      .catch(error => {
        console.error('Error:', error);
      });
  }
</script>
