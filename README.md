<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Glamour Salon - Book Your Appointment</title>
    <style>
        /* CSS Reset and Variables */
        :root {
            --primary: #d4af37;
            --secondary: #6c757d;
            --light: #f8f9fa;
            --dark: #343a40;
            --success: #28a745;
            --font-main: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-main);
            line-height: 1.6;
            color: var(--dark);
            background-color: #fff;
        }

        a {
            text-decoration: none;
            color: var(--primary);
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--dark);
        }

        .logo span {
            color: var(--primary);
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
        }

        .nav-link {
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-link:hover {
            color: var(--primary);
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23d4af37" opacity="0.2"/></svg>');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 5rem 1rem;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 1.5rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s;
        }

        .btn:hover {
            background-color: #c19b2e;
            transform: translateY(-2px);
        }

        /* Sections */
        section {
            padding: 5rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2rem;
            color: var(--dark);
            position: relative;
            padding-bottom: 1rem;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background-color: var(--primary);
        }

        /* About Section */
        .about-content {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            align-items: center;
        }

        .about-text {
            flex: 1;
            min-width: 300px;
        }

        .about-image {
            flex: 1;
            min-width: 300px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Services Section */
        .services {
            background-color: var(--light);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        .service-content {
            padding: 1.5rem;
        }

        .service-content h3 {
            margin-bottom: 0.5rem;
            color: var(--dark);
        }

        .price {
            color: var(--primary);
            font-weight: bold;
            font-size: 1.2rem;
            margin: 0.5rem 0;
        }

        /* Booking Section */
        .booking {
            background: linear-gradient(to right, #fff 50%, var(--light) 50%);
        }

        .booking-container {
            display: flex;
            flex-wrap: wrap;
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
        }

        .booking-image {
            flex: 1;
            min-width: 300px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23f8f9fa"/><path d="M30,30 L70,30 L70,70 L30,70 Z" fill="%23d4af37" opacity="0.2"/></svg>');
            background-size: cover;
        }

        .booking-form {
            flex: 1;
            min-width: 300px;
            padding: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-family: inherit;
        }

        /* Confirmation Message */
        .confirmation {
            display: none;
            text-align: center;
            padding: 2rem;
            background-color: var(--light);
            border-radius: 8px;
            margin-top: 2rem;
        }

        .confirmation h3 {
            color: var(--success);
            margin-bottom: 1rem;
        }

        /* Admin Page */
        .admin-section {
            padding: 2rem;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-top: 2rem;
            display: none;
        }

        .bookings-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }

        .bookings-table th, 
        .bookings-table td {
            padding: 0.75rem;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        .bookings-table th {
            background-color: var(--light);
            font-weight: 600;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 3rem 0 2rem;
        }

        .footer-content {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: space-between;
            margin-bottom: 2rem;
        }

        .footer-column {
            flex: 1;
            min-width: 200px;
        }

        .footer-column h3 {
            margin-bottom: 1rem;
            position: relative;
            padding-bottom: 0.5rem;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }

            .nav-menu {
                position: fixed;
                top: 70px;
                right: -100%;
                flex-direction: column;
                background-color: white;
                width: 80%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
                padding: 2rem 0;
                gap: 0;
            }

            .nav-menu.active {
                right: 0;
            }

            .nav-item {
                margin: 1rem 0;
            }

            .booking {
                background: #fff;
            }

            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <a href="#" class="logo">Glamour<span>Salon</span></a>
                <ul class="nav-menu">
                    <li class="nav-item"><a href="#" class="nav-link">Home</a></li>
                    <li class="nav-item"><a href="#about" class="nav-link">About</a></li>
                    <li class="nav-item"><a href="#services" class="nav-link">Services</a></li>
                    <li class="nav-item"><a href="#booking" class="nav-link">Book Now</a></li>
                    <li class="nav-item"><a href="#" class="nav-link" id="admin-link">Admin</a></li>
                </ul>
                <div class="hamburger">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Experience Luxury Beauty Services</h1>
            <p>Indulge in our premium salon treatments designed to enhance your natural beauty and provide ultimate relaxation.</p>
            <a href="#booking" class="btn">Book an Appointment</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Our Salon</h2>
            </div>
            <div class="about-content">
                <div class="about-text">
                    <p>Welcome to Glamour Salon, where beauty meets relaxation. Established in 2010, we have been providing top-quality beauty services to our valued clients for over a decade.</p>
                    <p>Our team of experienced professionals is dedicated to helping you look and feel your best. We use only premium products and the latest techniques to ensure exceptional results.</p>
                    <p>At Glamour Salon, we believe that self-care is not a luxury but a necessity. Our tranquil environment is designed to provide you with a peaceful escape from your busy life.</p>
                </div>
                <div class="about-image">
                    <!-- Placeholder for salon image -->
                    <div style="height: 300px; background-color: #f0f0f0; display: flex; align-items: center; justify-content: center;">
                        <span>Salon Interior Image</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <div class="container">
            <div class="section-title">
                <h2>Our Services</h2>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-content">
                        <h3>Haircut & Styling</h3>
                        <p>Professional haircut, wash, and blow-dry styling</p>
                        <div class="price">$45 - $75</div>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-content">
                        <h3>Hair Coloring</h3>
                        <p>Full color, highlights, balayage, or ombre</p>
                        <div class="price">$75 - $150</div>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-content">
                        <h3>Manicure & Pedicure</h3>
                        <p>Luxurious nail care with massage and polish</p>
                        <div class="price">$35 - $65</div>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-content">
                        <h3>Facial Treatment</h3>
                        <p>Rejuvenating facial customized to your skin type</p>
                        <div class="price">$60 - $100</div>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-content">
                        <h3>Waxing</h3>
                        <p>Professional waxing for smooth, hair-free skin</p>
                        <div class="price">$25 - $80</div>
                    </div>
                </div>
                <div class="service-card">
                    <div class="service-content">
                        <h3>Makeup Application</h3>
                        <p>Professional makeup for special occasions</p>
                        <div class="price">$55 - $95</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Section -->
    <section id="booking">
        <div class="container">
            <div class="section-title">
                <h2>Book Your Appointment</h2>
            </div>
            <div class="booking-container">
                <div class="booking-image">
                    <!-- Placeholder for booking image -->
                    <div style="height: 100%; min-height: 400px; background-color: #f8f9fa; display: flex; align-items: center; justify-content: center;">
                        <span>Booking Image</span>
                    </div>
                </div>
                <div class="booking-form">
                    <form id="booking-form">
                        <div class="form-group">
                            <label for="name">Full Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="service">Select Service</label>
                            <select id="service" class="form-control" required>
                                <option value="">Choose a service</option>
                                <option value="Haircut & Styling">Haircut & Styling</option>
                                <option value="Hair Coloring">Hair Coloring</option>
                                <option value="Manicure & Pedicure">Manicure & Pedicure</option>
                                <option value="Facial Treatment">Facial Treatment</option>
                                <option value="Waxing">Waxing</option>
                                <option value="Makeup Application">Makeup Application</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="date">Preferred Date</label>
                            <input type="date" id="date" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="time">Preferred Time</label>
                            <input type="time" id="time" class="form-control" required>
                        </div>
                        <button type="submit" class="btn">Book Appointment</button>
                    </form>
                    
                    <div id="confirmation" class="confirmation">
                        <h3>Thank You for Your Booking!</h3>
                        <p>Your appointment has been successfully scheduled. We've sent a confirmation to your email.</p>
                        <p>We look forward to seeing you at the salon!</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Admin Section -->
    <section id="admin" style="display: none;">
        <div class="container">
            <div class="section-title">
                <h2>Admin Dashboard</h2>
            </div>
            <div class="admin-section">
                <h3>All Bookings</h3>
                <table class="bookings-table">
                    <thead>
                        <tr>
                            <th>Name</th>
                            <th>Email</th>
                            <th>Service</th>
                            <th>Date</th>
                            <th>Time</th>
                        </tr>
                    </thead>
                    <tbody id="bookings-list">
                        <!-- Bookings will be populated here -->
                    </tbody>
                </table>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Glamour Salon</h3>
                    <p>Providing premium beauty services since 2010. Our mission is to enhance your natural beauty and provide a relaxing experience.</p>
                </div>
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <p>123 Beauty Street, City</p>
                    <p>Phone: (555) 123-4567</p>
                    <p>Email: info@glamoursalon.com</p>
                </div>
                <div class="footer-column">
                    <h3>Opening Hours</h3>
                    <p>Monday - Friday: 9am - 7pm</p>
                    <p>Saturday: 10am - 6pm</p>
                    <p>Sunday: 11am - 4pm</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2023 Glamour Salon. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.1/firebase-firestore.js"></script>

    <script>
        // Firebase configuration
        const firebaseConfig = {
            apiKey: "AIzaSyBRk5sD_d01bGaX_wMhTECNnGCYVYO7aPw",
authDomain: "barberboki-c9be8.firebaseapp.com",
projectId: "barberboki-c9be8",
storageBucket: "barberboki-c9be8.firebasestorage.app",
messagingSenderId: "477599830326",
appId: "1:477599830326:web:5b21ebeb02d3a563d06397"
};

        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);
        const db = firebase.firestore();

        // DOM Elements
        const bookingForm = document.getElementById('booking-form');
        const confirmation = document.getElementById('confirmation');
        const adminLink = document.getElementById('admin-link');
        const adminSection = document.getElementById('admin');
        const bookingsList = document.getElementById('bookings-list');
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');

        // Mobile Menu Toggle
        hamburger.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });

        // Admin Link Click
        adminLink.addEventListener('click', (e) => {
            e.preventDefault();
            document.querySelectorAll('section').forEach(section => {
                section.style.display = 'none';
            });
            adminSection.style.display = 'block';
            loadBookings();
        });

        // Form Submission
        bookingForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const phone = document.getElementById('phone').value;
            const service = document.getElementById('service').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            
            // Save booking to Firestore
            db.collection('bookings').add({
                name,
                email,
                phone,
                service,
                date,
                time,
                timestamp: firebase.firestore.FieldValue.serverTimestamp()
            })
            .then((docRef) => {
                console.log('Booking saved with ID: ', docRef.id);
                
                // Show confirmation message
                bookingForm.style.display = 'none';
                confirmation.style.display = 'block';
                
                // Reset form
                bookingForm.reset();
            })
            .catch((error) => {
                console.error('Error adding booking: ', error);
                alert('There was an error with your booking. Please try again.');
            });
        });

        // Load bookings for admin
        function loadBookings() {
            db.collection('bookings').orderBy('timestamp', 'desc').get()
            .then((querySnapshot) => {
                bookingsList.innerHTML = '';
                querySnapshot.forEach((doc) => {
                    const booking = doc.data();
                    const row = document.createElement('tr');
                    row.innerHTML = `
                        <td>${booking.name}</td>
                        <td>${booking.email}</td>
                        <td>${booking.service}</td>
                        <td>${booking.date}</td>
                        <td>${booking.time}</td>
                    `;
                    bookingsList.appendChild(row);
                });
            })
            .catch((error) => {
                console.error('Error getting bookings: ', error);
            });
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    navMenu.classList.remove('active');
                }
            });
        });
    </script>
</body>
</html>
