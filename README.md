Recipe UI & Backend Application
Project Overview
The Recipe UI & Backend Application is a full-stack project that showcases various cuisines, allowing users to browse and learn about different recipes. The project features a beautiful, interactive UI that displays recipe details including cuisine type, calorie information, and instructions. The backend is powered by a Spring Boot REST API that serves recipe data, allowing the UI to dynamically fetch recipes based on selected filters.

Features
Browse Recipes by Cuisine: Users can filter recipes by selecting from a variety of available cuisines.
Detailed Recipe Information: Each recipe card provides details such as the cuisine type, calorie count, and cooking instructions.
Interactive Recipe Modal: For each recipe, users can click "Show More" to view detailed cooking instructions in a modal popup.
Elegant UI: Modern, visually appealing user interface with responsive design, suitable for multiple devices.
Image Integration: Each recipe card is enhanced by an associated recipe image, with fallback mechanisms for missing images.
Technologies Used
Frontend
React: The user interface is built using React, taking advantage of reusable components for scalability.
CSS: The interface is styled with custom CSS, featuring transitions and responsive layouts for a better user experience.
React Router: For navigation between different parts of the application.
Backend
Spring Boot: Java Spring Boot framework is used to create RESTful APIs that provide recipe data to the frontend.
H2 Database: An in-memory H2 database is used to store and serve recipe data. The data is currently set up as in-memory, making it suitable for testing and development.
JPA/Hibernate: To manage interactions with the database, JPA (Java Persistence API) is used, which provides a convenient abstraction over Hibernate ORM.
Database
H2 In-Memory Database: Recipes are stored in an H2 in-memory database, making it easy to modify and test during development. However, the data will be lost upon restart unless it's modified to use a persistent storage solution.
Installation and Setup
Prerequisites
Ensure you have the following installed:

Node.js (>= 14.x.x): For running the frontend.
Java Development Kit (JDK 11 or newer): For running the Spring Boot backend.
Maven: To build and manage dependencies for the backend.
IDE/Text Editor: Recommended for easy code navigation and debugging.
Setup Instructions
Backend
Clone the repository:

bash
Copy code
git clone https://github.com/your-repo/recipe-project.git
Navigate to the backend folder:

bash
Copy code
cd recipe-project/recipes-backend
Build the backend using Maven:

bash
Copy code
mvn clean install
Run the Spring Boot application:

bash
Copy code
mvn spring-boot:run
The backend server will run at http://localhost:8080.

Access the H2 console for testing:

bash
Copy code
URL: http://localhost:8080/h2-console
Username: sa
Password: password
Update the database from memory to persistent storage if necessary by changing configurations in application.properties.

Frontend
Navigate to the frontend folder:
bash
Copy code
cd ../recipes-ui
Install dependencies:
bash
Copy code
npm install
Start the development server:
bash
Copy code
npm start
The frontend will run at http://localhost:3000.
File Structure
bash
Copy code
recipe-project/
│
├── recipes-backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   ├── com.example.recipes_backend/      # Controllers, Services, Models
│   │   │   └── resources/
│   │   │       └── application.properties           # Spring Boot configuration
│   └── pom.xml                                      # Backend dependencies
│
├── recipes-ui/
│   ├── public/
│   │   └── images/recipes                           # Folder containing recipe images
│   ├── src/
│   │   ├── components/                              # React components like RecipeCard, Grid, Navbar, Modal, etc.
│   │   ├── api/                                     # API calls to fetch recipes
│   │   ├── utils/                                   # Utility files like imageMapping.js
│   │   └── App.js                                   # Main React app file
│   └── package.json                                 # Frontend dependencies
└── README.md
API Endpoints
The following endpoints are exposed by the backend to serve recipe data:

Get All Recipes: GET /api/recipes
Get Recipes by Cuisine: GET /api/recipes?cuisine={cuisineType}
These endpoints power the dynamic loading of recipe data on the frontend, based on user interactions.

Configuration Notes
H2 In-Memory Database: The current configuration uses an in-memory H2 database (jdbc:h2:mem:recipesdb). If persistent storage is required, modify the configuration in application.properties to use a file-based H2 database or switch to a production database like MySQL/PostgreSQL.

React Router & State Management: The frontend uses React Router to navigate between different pages seamlessly. Recipe data is managed via hooks (useState and useEffect) to facilitate efficient data loading and updates.

Deployment
Backend Deployment
Create a .jar file with Maven:
bash
Copy code
mvn clean package
Deploy the .jar file on a server environment like AWS EC2, Heroku, or any server supporting Java runtime.
Frontend Deployment
Build the production version:
bash
Copy code
npm run build
Serve the static files using services like Netlify, Vercel, or using a Node.js server.
Future Improvements
Persistent Storage: Switch to a more scalable database solution like MySQL or PostgreSQL to ensure data persists across server restarts.
User Authentication: Add user login and registration, allowing users to save their favorite recipes.
Recipe Submission: Allow users to contribute their own recipes through a form in the frontend.
Enhanced Styling: Implement additional UI/UX improvements such as better animations, dark/light mode, and improved card transitions.
Troubleshooting
Images Not Loading: Make sure all image paths are correctly set in public/images/recipes and mapped accurately in imageMapping.js.
H2 Console Not Accessible: Verify the H2 configuration is enabled (spring.h2.console.enabled=true) in application.properties.
Backend Not Connecting: Ensure the backend server is running before starting the frontend, and check that both frontend and backend are pointing to correct addresses (http://localhost:8080).
Contribution
If you wish to contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/my-feature).
Commit your changes (git commit -am 'Add some feature').
Push to the branch (git push origin feature/my-feature).
Open a Pull Request.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
React.js Documentation for UI guidance.
Spring Boot Documentation for backend references.
H2 Database for in-memory testing capabilities.
Enjoy cooking with a variety of cuisines and exploring recipes with this interactive application! 🍕🥗🍰
