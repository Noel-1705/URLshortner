# URL Shortener with Visit Tracking

A simple web-based URL Shortener built using Python, Flask, and SQLite. This application allows users to convert long URLs into short, shareable links and track the number of times each shortened URL has been visited.

## Features

* Convert long URLs into short and unique links
* Redirect users to the original URL when the short link is accessed
* Store URL mappings using SQLite
* Track the number of visits for each shortened URL
* Responsive user interface using Bootstrap
* Beginner-friendly implementation using Flask and SQLAlchemy

## Technologies Used

* Python
* Flask
* Flask-SQLAlchemy
* SQLite
* HTML
* Bootstrap 4
* Jinja2 Templates

## Project Structure

```text
URLshortner/
│
├── templates/
│   ├── base.html
│   ├── home.html
│   └── shorturl.html
│
├── app.py
├── urls.db
└── README.md
```

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Noel-1705/URLshortner.git
cd URLshortner
```

### 2. Create a Virtual Environment (Optional)

```bash
python -m venv venv
```

Activate the virtual environment:

**Windows**

```bash
venv\Scripts\activate
```

**Linux/macOS**

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install flask flask-sqlalchemy
```

### 4. Run the Application

```bash
python app.py
```

### 5. Open in Browser

```text
http://127.0.0.1:5000
```

## How the Application Works

### Step 1: Enter a Long URL

The user enters a long URL through the homepage form.

Example:

```text
https://www.example.com/articles/python/flask-tutorial
```

### Step 2: Check Existing URLs

The application checks whether the URL has already been shortened.

* If it exists, the previously generated short URL is returned.
* Otherwise, a new short URL is created.

### Step 3: Generate a Short URL

A random 3-character code consisting of uppercase and lowercase letters is generated.

Example:

```text
aBc
```

### Step 4: Store Data

The original URL and generated short code are stored in the SQLite database.

Example:

```text
Original URL: https://www.example.com/articles/python/flask-tutorial
Short URL: aBc
```

### Step 5: Display the Shortened URL

The application displays the generated short URL to the user.

Example:

```text
http://127.0.0.1:5000/aBc
```

### Step 6: Redirect Users

When someone visits the shortened URL, Flask searches the database for the corresponding original URL and redirects the user.

Example:

```text
http://127.0.0.1:5000/aBc
```

Redirects to:

```text
https://www.example.com/articles/python/flask-tutorial
```

### Step 7: Track Visits

Every time a shortened URL is accessed:

1. The application locates the URL in the database.
2. The visit counter is incremented.
3. The user is redirected to the original website.

This provides a simple analytics feature that tracks URL usage.

## Database

The application uses SQLite for storing data.

Database file:

```text
urls.db
```

Each record stores:

| Field  | Description         |
| ------ | ------------------- |
| id_    | Unique identifier   |
| long   | Original URL        |
| short  | Generated short URL |
| clicks | Number of visits    |

Example:

```text
ID: 1
Original URL: https://www.google.com
Short URL: aBc
Visits: 15
```

## Flask Concepts Demonstrated

This project demonstrates several important Flask concepts:

### Routing

Handles navigation between pages and URL redirection.

### Template Inheritance

Uses Jinja2 templates with a common base layout.

### Form Handling

Accepts user input through HTML forms.

### Database Integration

Stores and retrieves data using Flask-SQLAlchemy.

### URL Redirection

Redirects users from shortened URLs to the original URLs.

### Analytics

Tracks the number of visits for each shortened URL.

## Learning Outcomes

By building this project, you can learn:

* Flask fundamentals
* Web routing
* Jinja2 templating
* Form processing
* SQLite database integration
* Flask-SQLAlchemy ORM
* URL redirection
* Database querying
* Visit tracking and analytics
* Basic web application architecture

## Future Improvements

* User authentication and accounts
* Custom short URLs
* Detailed analytics dashboard
* URL expiration dates
* QR code generation
* REST API support
* Search functionality
* Export analytics reports

## Author

**Noel Biju**

Computer Science Student

GitHub: https://github.com/Noel-1705/URLShortner

## License

This project is open-source and available for educational and learning purposes.
