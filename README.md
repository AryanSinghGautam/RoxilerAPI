Backend Task Overview

To create the backend for the Roxiler System Assessment, we will implement several APIs to handle data initialization, transaction listing, statistics, and chart data. Below is a structured approach to each task.

1. Initialize Database API

Endpoint: POST /api/initialize
Functionality:
Fetch JSON data from the third-party API.
Parse the data and define an efficient table structure.
Store the data in the database.
Table Structure:
Transactions Table:
id: Integer (Primary Key)

title: String

price: Float

description: String

category: String

image: String

sold: Boolean

dateOfSale: DateTime

2. List Transactions API

Endpoint: GET /api/transactions
Parameters:
month: String (January to December)
page: Integer (default: 1)
perPage: Integer (default: 10)
search: String (optional)
Functionality:
Filter transactions by dateOfSale month.

Support search functionality on title, description, and price.

Implement pagination to return results based on the page number.

3. Statistics API

Endpoint: GET /api/statistics
Parameters:
month: String (January to December)
Functionality:
Calculate and return:
Total sale amount for the selected month.

Total number of sold items for the selected month.

Total number of not sold items for the selected month.

4. Bar Chart Data API

Endpoint: GET /api/bar-chart
Parameters:
month: String (January to December)
Functionality:
Return the number of items in specified price ranges for the selected month:
0 - 100

101 - 200

201 - 300

301 - 400

401 - 500

501 - 600

601 - 700

701 - 800

801 - 900

901-above

5. Pie Chart Data API

Endpoint: GET /api/pie-chart
Parameters:
month: String (January to December)
Functionality:
Return unique categories and the number of items in each category for the selected month.

6. Combined Data API

Endpoint: GET /api/combined-data
Parameters:
month: String (January to December)
Functionality:
Fetch data from the three APIs above and combine the responses into a single JSON object.

Frontend Task Overview

The frontend will utilize the APIs created above to display transaction data, statistics, and charts on a single page.

1. Transactions Table

Functionality:
Use the transactions listing API to populate the table.

Include a dropdown for month selection (default: March).

Implement a search box for filtering transactions.

Include pagination controls (Next and Previous).

2. Transactions Statistics

Functionality:
Display total sales, total sold items, and total not sold items for the selected month using the statistics API.

3. Transactions Bar Chart

Functionality:
Display a bar chart showing price ranges and the number of items in each range for the selected month using the bar chart API.

4. Design Considerations

Implement a clean and user-friendly design.

Ensure responsiveness for various screen sizes.

Follow the mockup provided while allowing for creative design improvements.

Conclusion

This structured approach outlines the backend and frontend tasks required for the Roxiler System Assessment. Each API is designed to handle specific functionalities, ensuring a seamless integration between the frontend and backend components.
