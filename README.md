# Modern Web Development Bootcamp

## Day 1: Building the Foundation

### 1. HTML Basics
#### **Portfolio Structure**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio</title>
</head>
<body>
    <header>
        <h1>My Portfolio</h1>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="about">
            <h2>About Me</h2>
            <p>Hi, I'm a web developer passionate about creating amazing websites.</p>
        </section>
        <section id="projects">
            <h2>Projects</h2>
            <ul>
                <li>Project 1: Awesome Website</li>
                <li>Project 2: Cool App</li>
            </ul>
        </section>
        <section id="contact">
            <h2>Contact</h2>
            <p>Email: <a href="mailto:youremail@example.com">youremail@example.com</a></p>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 My Portfolio</p>
    </footer>
</body>
</html>
```

### 2. CSS Basics
#### **Custom Styles for Portfolio**
```css
/* styles.css */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    background-color: #f4f4f9;
    color: #333;
}
header {
    background: #333;
    color: #fff;
    padding: 1rem;
}
header h1 {
    margin: 0;
}
nav ul {
    list-style: none;
    padding: 0;
}
nav ul li {
    display: inline;
    margin-right: 1rem;
}
nav ul li a {
    color: #fff;
    text-decoration: none;
}
main {
    padding: 1rem;
}
footer {
    text-align: center;
    margin-top: 1rem;
    padding: 1rem;
    background: #333;
    color: #fff;
}
```

#### **HTML with Linked CSS**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Same as previous HTML -->
</body>
</html>
```

---

## Day 2: Adding Style and Interactivity

### 1. TailwindCSS Setup
#### **TailwindCSS Integration**
- Install TailwindCSS:
```bash
npm install -D tailwindcss
npx tailwindcss init
```
- **`tailwind.config.js`**
```javascript
module.exports = {
  content: ["./*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```
- **TailwindCSS File**
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### **Redesign Portfolio with TailwindCSS**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 text-gray-800">
    <header class="bg-gray-900 text-white p-4">
        <h1 class="text-xl">My Portfolio</h1>
        <nav>
            <ul class="flex space-x-4">
                <li><a href="#about" class="hover:text-yellow-500">About</a></li>
                <li><a href="#projects" class="hover:text-yellow-500">Projects</a></li>
                <li><a href="#contact" class="hover:text-yellow-500">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main class="p-4">
        <section id="about" class="mb-4">
            <h2 class="text-2xl font-bold">About Me</h2>
            <p>Hi, I'm a web developer passionate about creating amazing websites.</p>
        </section>
        <section id="projects" class="mb-4">
            <h2 class="text-2xl font-bold">Projects</h2>
            <ul class="list-disc pl-5">
                <li>Project 1: Awesome Website</li>
                <li>Project 2: Cool App</li>
            </ul>
        </section>
        <section id="contact">
            <h2 class="text-2xl font-bold">Contact</h2>
            <p>Email: <a href="mailto:youremail@example.com" class="text-blue-500 hover:underline">youremail@example.com</a></p>
        </section>
    </main>
    <footer class="text-center bg-gray-900 text-white p-4">
        <p>&copy; 2024 My Portfolio</p>
    </footer>
</body>
</html>
```

### 2. JavaScript Basics
#### **Add Interactivity**
```html
<script>
    document.querySelectorAll('nav ul li a').forEach(link => {
        link.addEventListener('click', () => {
            alert('Navigating to ' + link.textContent);
        });
    });
</script>
```

---

## Day 3: Full-Stack Web Development

### 1. Next.js Basics
#### **Create a Next.js App**
```bash
npx create-next-app@latest my-next-portfolio
cd my-next-portfolio
npm run dev
```

#### **Portfolio Page in Next.js**
```javascript
// pages/index.js
import Head from 'next/head';

export default function Home() {
    return (
        <div>
            <Head>
                <title>My Portfolio</title>
            </Head>
            <header className="bg-gray-900 text-white p-4">
                <h1 className="text-xl">My Portfolio</h1>
            </header>
            <main className="p-4">
                <section id="about" className="mb-4">
                    <h2 className="text-2xl font-bold">About Me</h2>
                    <p>Hi, I'm a web developer passionate about creating amazing websites.</p>
                </section>
            </main>
            <footer className="text-center bg-gray-900 text-white p-4">
                <p>&copy; 2024 My Portfolio</p>
            </footer>
        </div>
    );
}
```

### 2. FastAPI Basics
#### **Setting Up FastAPI**
```bash
pip install fastapi uvicorn
```

#### **Simple API for Portfolio**
```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Welcome to My Portfolio API"}

@app.get("/projects")
def get_projects():
    return [
        {"name": "Awesome Website", "description": "A cool project"},
        {"name": "Cool App", "description": "Another cool project"}
    ]
```

#### **Running the Server**
```bash
uvicorn main:app --reload
```

### 3. Deployment
#### **Frontend Deployment on Vercel**
- Install Vercel CLI:
```bash
npm i -g vercel
```
- Deploy:
```bash
vercel
```

#### **Backend Deployment on Render**
- Create a `requirements.txt`:
```bash
fastapi
uvicorn
```
- Push to GitHub and connect to Render for deployment.

