## Flask Application Design for Flight Ticket Search and Booking

### HTML Files

- **index.html (Homepage):**
   - Contains the form for user to search for flights (origin, destination, departure date, return date)
   - Form submits to the '/search' route

- **search_results.html (Search Results):**
   - Displays a list of flight options that match the user's search criteria
   - Each flight option includes information such as airline, departure/arrival times, fares, and a "Book" button
   - The "Book" button triggers an AJAX call to the '/book' route

### Routes

- **@app.route('/') (Homepage):**
   - Renders the 'index.html' template

- **@app.route('/search', methods=['POST']):**
   - Receives the search criteria from the form on 'index.html'
   - Queries an API or database to retrieve flight options that match the criteria
   - Renders the 'search_results.html' template with the list of flight options

- **@app.route('/book', methods=['POST']):**
   - Receives the flight ID and other necessary details from the AJAX call triggered by the "Book" button on 'search_results.html'
   - Completes the booking process by interacting with a payment gateway or booking system
   - Returns a confirmation response or error message to the AJAX call