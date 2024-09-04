# CSD-casestudy
Hotel Management System Documentation
1. How to Run the Application
Prerequisites
• Ensure that Java Development Kit (JDK) is installed on your machine (JDK 8 or 
above).
• A text editor or an IDE (e.g., IntelliJ IDEA, Eclipse, NetBeans).
Steps to Run
1. Clone or Download the Project:
o Download the source code and save it in a directory on your system.
2. Compile the Source Code:
o Open a terminal/command prompt.
o Navigate to the directory containing the source files.
o Compile the Java files using the command:
3. Run the Application:
o Execute the compiled Java classes using the command:
2. Instructions for Each Feature
1. Add and Remove Rooms
• Add a Room:
o From the main menu, select the option to add a new room.
o Provide the room details such as room number, room type, price per night, and 
availability.
o The system will confirm the addition of the room.
• Remove a Room:
o From the main menu, select the option to remove a room.
o Enter the ID of the room you wish to remove.
o The system will confirm the removal if the room exists.
2. Update Room Details
• Update Room:
o From the main menu, select the option to update room details.
o Enter the room ID and the new details you wish to update (e.g., room type, 
price).
o The system will confirm the update.
3. Check Room Availability
• Check Availability:
o From the main menu, select the option to check room availability.
o Enter the room number and the date range (start and end dates).
o The system will display whether the room is available for the given dates.
4. Make Reservations
• Make a Reservation:
o From the main menu, select the option to make a reservation.
o Provide the room ID, guest name, and the date range for the reservation.
o The system will confirm the reservation if the room is available.
5. Check-in and Check-out Guests
• Check-in Guest:
o From the main menu, select the option to check-in a guest.
o Enter the room ID and the guest’s name.
o The system will confirm the check-in if the reservation exists.
• Check-out Guest:
o From the main menu, select the option to check-out a guest.
o Enter the room ID.
o The system will confirm the check-out and mark the room as available.
3. Explanation of Exception Handling
1. Input Validation
• The application validates user input at each step to ensure that only correct and 
meaningful data is processed. For example:
o When adding a room, the system checks if the room number is already in use.
o During reservation, the system ensures that the date range is valid (i.e., the 
start date is before the end date).
2. Exception Handling
• IllegalArgumentException:
o Used to handle scenarios where input values are not valid, such as negative 
room prices or invalid dates.
o Example: If a user tries to create a reservation with an end date earlier than the 
start date, an IllegalArgumentException is thrown with an appropriate error 
message.
• NoSuchElementException:
o Thrown when trying to access a room or reservation that does not exist in the 
system.
o Example: If a user tries to remove a room that isn’t present, a 
NoSuchElementException is thrown.
• Custom Exceptions:
o You may implement custom exceptions to handle specific errors, such as 
RoomNotAvailableException for situations where a room is already booked 
for the requested dates.
o These exceptions provide clear, understandable error messages to the user and 
prevent the application from crashing.
3. Try-Catch Blocks
• Throughout the application, try-catch blocks are used to catch and handle exceptions 
gracefully.
o Example: When reading user input for room details, the system uses a try￾catch block to handle NumberFormatException if the user inputs non-numeric 
data where a number is expected.
4. Ensuring Application Stability
• All exceptions are caught and handled in a way that informs the user of what went 
wrong while allowing the application to continue running.
• The system is designed to return to the main menu after handling an error, ensuring 
that the user can try again without restarting the application.
Explanation: How OOP is implemented
The Hotel Management System is a console-based application designed to assist hotel staff in 
managing room details, reservations, and guest check-ins/check-outs. The system is built 
using Core Java, leveraging Object-Oriented Programming (OOP) principles to ensure 
modularity, scalability, and maintainability.
2. Application Design
2.1 Class Design
The application is designed around three primary classes: Room, Reservation, and 
HotelManagementSystem. Each class is responsible for managing specific aspects of the 
hotel management process.
• Room Class:
o Attributes: id, roomNumber, roomType, pricePerNight, isAvailable.
o Methods: This class includes constructors, getters, setters, and a toString
method to represent room details.
o Responsibilities: The Room class represents individual rooms in the hotel, 
encapsulating all the necessary details.
• Reservation Class:
o Attributes: id, roomId, guestName, startDate, endDate.
o Methods: Similar to the Room class, this includes constructors, getters, 
setters, and a toString method.
o Responsibilities: The Reservation class manages booking information, linking 
a specific room to a guest for a particular date range.
• HotelManagementSystem Class:
o Attributes: HashMap<Integer, Room> rooms, ArrayList<Reservation> 
reservations.
o Methods:
▪ addRoom(Room room), removeRoom(int roomId), updateRoom(int 
roomId, Room updatedRoom).
▪ checkRoomAvailability(int roomNumber, LocalDate startDate, 
LocalDate endDate).
▪ makeReservation(int roomId, String guestName, LocalDate startDate, 
LocalDate endDate).
▪ checkInGuest(int roomId, String guestName), checkOutGuest(int 
roomId).
o Responsibilities: This class serves as the main controller, managing the 
collection of rooms and reservations, and providing the business logic to 
manage hotel operations.
2.2 Data Storage
• Java Collections:
o The system utilizes HashMap to store room details, allowing for efficient 
retrieval, addition, and removal of rooms.
o An ArrayList is used to manage reservations, providing dynamic resizing and 
easy iteration over existing bookings.
3. Object-Oriented Principles Applied
3.1 Encapsulation
• Implementation: Each class encapsulates its attributes and methods, restricting direct 
access to the data fields. Instead, data is accessed and modified through public getter 
and setter methods. This approach ensures that the internal state of each object is 
protected and can only be altered in controlled ways.
3.2 Abstraction
• Implementation: The system hides complex operations behind simple method calls. 
For example, checking room availability involves iterating over reservations and 
comparing dates, but this complexity is abstracted away behind a simple 
checkRoomAvailability() method.
3.3 Inheritance
• Potential Use: While the current implementation does not require inheritance due to 
the simple and distinct nature of the Room and Reservation classes, inheritance could 
be applied if the system were to be expanded. For instance, a SpecialRoom class 
could inherit from Room to represent rooms with additional features.
3.4 Polymorphism
• Potential Use: The design could leverage polymorphism if the system is extended to 
handle different types of reservations (e.g., StandardReservation, GroupReservation). 
These could be subclasses of a base Reservation class, with each type implementing 
its own version of methods like calculateTotalCost().
3.5 Modularity
• Implementation: The system is divided into modular classes, each with a clear 
responsibility. This modularity allows for easier maintenance and future 
enhancements, such as adding new features or modifying existing ones without 
affecting other parts of the system.
4. Conclusion
The Hotel Management System is designed with a clear focus on OOP principles, ensuring 
that the application is easy to understand, maintain, and extend. The use of encapsulation, 
abstraction, and modularity results in a robust system that can handle the essential functions 
of hotel management while being adaptable to future requirements.
