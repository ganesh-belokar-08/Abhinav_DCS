--> THE JSON PLACEHOLDER's are mainly used when we have to send our data over an api but our backend facility is not ready that time mainly we prefer to use the placeholders.
--> The placeholder provides a place to store the data in the form of an Array.

 // Mock data storage (simulates a backend database)
      let mockDatabase = [];

// Function to fetch and display data

      function fetchAndDisplayData() {
        $.ajax({
          url: 'https://jsonplaceholder.typicode.com/posts', // Mock API endpoint
          method: 'GET',
          success: function (response) {
            // Clear existing table rows
            $('#dataTable').empty();

            // Append rows from the mock database
            mockDatabase.forEach((data, index) => {
              let row = `<tr>
                <td>${index + 1}</td>
                <td>${data.productCode}</td>
                <td>${data.productName}</td>
                <td>${data.productDescription}</td>
                <td>${data.pricePerMeter}</td>
                <td>${data.productType}</td>
                <td>${data.unitType || "N/A"}</td>
                <td>${data.gstPercentage}%</td>
                <td>${data.usage}</td>
                <td>${data.totalPrice}</td>
              </tr>`;
              $('#dataTable').append(row);
            });
          },
          error: function (error) {
            console.error('Error fetching data:', error);
          }
        });
      }
