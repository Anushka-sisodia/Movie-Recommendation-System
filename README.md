# Movie-Recommendation-System

# SC2002 Object - Oriented Design and Programming
## MOBLIMA
### Movie Booking and Listing Management System 
### LAB GROUP SE3 - GROUP 6



Video Explanation: https://drive.google.com/file/d/1bQxXvxhmKUQxbYD4m_rrl73Flsm-wCv0/view?usp=sharing


#### 1. Introduction to Moblima
MOBLIMA is a non-GUI application created to make it easier to reserve and buy movie tickets as well as to serve admin users' administrative needs. One operator with numerous multiplexes located throughout Singapore can use this application.
We will go through a number of design principles in this report, as well as object-oriented ideas we used to build this application. A thorough UML Class diagram is also provided for examination to further highlight the application's functionality.

![moblimagit](https://github.com/Anushka-sisodia/Movie-Recommendation-System/assets/141212420/9b4118d2-472b-49e6-b77a-734ee17d5233)

#### 2. MVC Design Pattern
The Model View Controller (MVC) specifies that an application consist of a data model, presentation information, and control information. We have organised our source code into these categories respectively (Model, View and Controller packages).
● Model
Our entity classes were grouped into the Model category. Classes like Review and Showtime fall under this category. These classes mostly consist of pure data and has simple methods.
● View
Each menu in our application is regarded as a view which is managed by the view category. Few examples like MainMenuView and StaffListMoviesView fall under this category. These classes have methods which presents information to the user.
● Controller
These are classes which control most of the logic flow of the application. Our source code contains a total of 4 control classes.
  
1. DataBaseManager:
Our txt file or database is managed by DataBaseManager. This class mostly consists of static methods that aid in keeping data into text files and retrieving data from databases.
2. IOManager:
Any interaction with the application's user is handled by this class. It is made up of static methods that mostly deal with either obtaining user input or outputting data into the console screen. These methods also assist in handling certain exceptions which may arise when processing the user inputs.
3. PriceManager:
This class is responsible for explaining how prices are calculated. This takes into account both the calculation of the ticket price and the calculation of the order the moviegoer placed. The price of a ticket or order is influenced by a number of variables.
4. ViewsManager:
This class is in charge of controlling the application's flow of the various View classes. This class handles a number of operations, such as moving to the next view and returning to the previous views. This is accomplished by keeping track of a stack that houses the displayed views. Simply pop the current view off the views stack to access the previous view, and push the new view onto the stack to access the subsequent view.

#### 3. Object-Oriented Design

a. Abstraction
Abstraction is the process of reducing various specific characteristics to a set of essential characteristics. An example is the abstract method getFractionalCostOutOfOriginal in the Ticket class. We do not know exactly how to calculate the price of a “generic ticket” due to the lack of information. Hence that method is only implemented in its subclasses such as AdultTicket, ChildTicket and SCTicket where sufficient information is given to calculate the price of the different type of tickets.

b. Encapsulation
Encapsulation is used to protect an object’s data and hide the details or implementation from user. We achieve encapsulation by making all classes’ attributes private. These data can only be accessed and modified using the getter and setter methods which are public.
 
c. Inheritance
Inheritance describes a “is-a” relationship. We use inheritance as it allows us to write less repetitive codes. MainMenuView “is-a” BaseView while AdultTicket “is-a” Ticket. Hence MainMenuView and AdultTicket are subclasses of each of them respectively and inherits their properties (reuse some of their code).

d. Polymorphism
Polymorphism refers to the ability of an object to take on many forms. In OOP, it means an object/class can take on many different type. For example, the ticket class took on the form of AdultTicket, ChildTicket and SCTicket.
