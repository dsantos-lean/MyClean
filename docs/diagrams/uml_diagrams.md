# Explanation of UML Diagrams

## This document provides explanations for the two UML diagrams: a sequence diagram and a class diagram.

### 1. Sequence Diagram: Booking a Cleaning Service
### The sequence diagram illustrates the process of a user booking a cleaning service through the website.

![Sequence](https://github.com/user-attachments/assets/7050c9b7-dd60-4237-b9e5-a25cea120714)

#### Breakdown:
1. User Accesses Website: The user begins by accessing the website's homepage.
2. Homepage Options: The website's frontend presents the user with options such as registration, login, contact information, and a chatbox.
3. Navigate to Booking: The user navigates to the booking page, typically located at [website.com/booking](http://3.27.120.57/booking-page/).
4. Request Details: The booking page prompts the user to enter details about the desired service, including the service type, address, and date.
5. Submit Request: The user submits their booking request.
6. Fetch Cleaners: The booking page interacts with the database to retrieve a list of available cleaners that match the user's criteria.
7. Return Cleaner List: The database returns the list of available cleaners to the booking page.
8. Redirect to Cleaner List: The booking page redirects the user to the cleaner list page, located at [website.com/available-cleaners](http://3.27.120.57/available-cleaners/).
9. Display Cleaners: The cleaner list page displays the available cleaners and provides options for the user to book a specific cleaner.
10. Select Cleaner: The user selects a cleaner from the list and clicks the 'Book' option.
11. Redirect to Payment: The cleaner list page redirects the user to the payment page.
12. Enter Payment Details: The user enters their payment details on the payment page.
13. Process Transaction: The payment page processes the transaction by interacting with the database.
14. Booking Confirmation: The database sends a booking confirmation to the user. __Not implemented__
15. Logout (Optional): The user may choose to log out of the website.



### 2. Class Diagram: System Entities
### The class diagram describes the main entities (classes) within the system and their relationships.

![Class](https://github.com/user-attachments/assets/3a738c13-b051-44a8-af74-26aafef471c7)


#### Breakdown:
1. Class Descriptions:User: Represents a user of the system. Attributes include avatar, username, password, name, email, and role. Operations include register(), login(), updateProfile(), and logout().
2. Cleaner: Represents a cleaner, inheriting from User. Includes attributes for rate, availability, specialization, and website.
3. CleaningCompany: Represents a cleaning company, inheriting from User. Includes attributes for rate, availability, specialization, and website. Also includes an operation to manageCleaners().4. Booking: Represents a booking made by a user. Attributes include bookingID, customerID, cleanerID, serviceType, address, date, and status. Operations include confirmBooking() and cancelBooking().
5. Payment: Represents a payment for a booking. Attributes include paymentID, bookingID, amount, method, and status. Operation is processPayment().
6. Chatbox: Represents the chatbox functionality for user communication. Operations include sendMessage() and receiveMessage().
7. ReportRefund: Represents the functionality for users to request refunds or report issues. Operations include requestRefund() and reportIssue().

#### Relationships:
- Inheritance: Cleaner and CleaningCompany inherit from User.
- Association:
    - User makes Booking.
    - Booking assigns a Cleaner.
    - Booking triggers Payment.
    - User interacts with Chatbox.
    - User can access ReportRefund (when logged in).
