# Multi-page-website

For Milestone 2, here’s a step-by-step guide to build a simple multi-page website using React, along with custom CSS for responsiveness.

1. Set Up React Project:
If you haven't already created a React project, start by setting up a new one.

bash
Copy code
npx create-react-app my-multi-page-website
cd my-multi-page-website
npm start
This will create the basic React setup for your project.

2. Create Pages and Components:
You’ll need different pages (e.g., Home, About, Contact) and reusable components (like a Navbar, Footer, etc.).

Create a components folder inside src to store common components like the navbar and footer.
Create a pages folder to store different page components like HomePage, AboutPage, ContactPage.
Example:
Navbar Component (src/components/Navbar.js):

jsx
Copy code
import React from 'react';
import { Link } from 'react-router-dom';

const Navbar = () => {
    return (
        <nav>
            <ul>
                <li><Link to="/">Home</Link></li>
                <li><Link to="/about">About</Link></li>
                <li><Link to="/contact">Contact</Link></li>
            </ul>
        </nav>
    );
};

export default Navbar;
HomePage Component (src/pages/HomePage.js):

jsx
Copy code
import React from 'react';

const HomePage = () => {
    return (
        <div>
            <h1>Welcome to the Home Page</h1>
        </div>
    );
};

export default HomePage;
AboutPage Component (src/pages/AboutPage.js):

jsx
Copy code
import React from 'react';

const AboutPage = () => {
    return (
        <div>
            <h1>About Us</h1>
            <p>This is the About Page.</p>
        </div>
    );
};

export default AboutPage;
ContactPage Component (src/pages/ContactPage.js):

jsx
Copy code
import React from 'react';

const ContactPage = () => {
    return (
        <div>
            <h1>Contact Us</h1>
            <p>This is the Contact Page.</p>
        </div>
    );
};

export default ContactPage;
3. Routing:
To navigate between pages, you'll need React Router.

bash
Copy code
npm install react-router-dom
In your src/App.js, set up the routing:

jsx
Copy code
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Navbar from './components/Navbar';
import HomePage from './pages/HomePage';
import AboutPage from './pages/AboutPage';
import ContactPage from './pages/ContactPage';

function App() {
    return (
        <Router>
            <Navbar />
            <Routes>
                <Route path="/" element={<HomePage />} />
                <Route path="/about" element={<AboutPage />} />
                <Route path="/contact" element={<ContactPage />} />
            </Routes>
        </Router>
    );
}

export default App;
4. Custom CSS for Styling and Responsiveness:
You can create a custom CSS file for styling and make the website responsive.

Create a styles.css file in the src folder and import it into your App.js file.
Example styles.css:

css
Copy code
/* Global Styles */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

nav {
    background-color: #333;
    padding: 10px;
}

nav ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    text-align: center;
}

nav ul li {
    display: inline;
    margin-right: 20px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

h1 {
    text-align: center;
}

/* Responsive Styles */
@media (max-width: 768px) {
    nav ul li {
        display: block;
        margin: 10px 0;
    }
}
Import the CSS in App.js:
javascript
Copy code
import './styles.css';
5. Run the App:
Now, you can run the app and check the multi-page functionality:

bash
Copy code
npm start
Your pages should now have:

A Navbar to navigate between pages.
Custom CSS styling with responsiveness (using media queries to adjust layout for smaller screens).
React Router handling page routing.
Summary:
Components: Navbar, Footer, etc.
Pages: Home, About, Contact.
Custom CSS: Applied globally and responsively for mobile-first design.
React Router: Used to navigate between pages.
