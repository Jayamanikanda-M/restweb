# Ex.07 Restaurant Website
## Date:

## AIM:
To develop a static Restaurant website to display the food items and services provided by them.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS.

### Step 3:
Updating the sample content.

### Step 4:
Choose the appropriate style and color scheme.

### Step 5:
Validate the layout in various browsers.

### Step 6:
Validate the HTML code.

### Step 7:
Publish the website in the given URL.

## PROGRAM:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Majestic Luxury Restaurant</title>
    
    <style>
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Montserrat', sans-serif; color: #fff; background-color: #111; }
        a { text-decoration: none; color: inherit; }

        
        header {
            height: 100vh;
            background: url('https://images.unsplash.com/photo-1600891964599-f61ba0e24092?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8bGF4dXJ5JTIwcmVzdGF1cmFudHxlbnwwfHwwfHw%3D&ixlib=rb-4.0.3&q=80&w=1080') center/cover no-repeat;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
        }
        header::after {
            content: "";
            position: absolute;
            top:0; left:0;
            width:100%; height:100%;
            background: rgba(0,0,0,0.5);
        }
        header .hero-content {
            position: relative;
            z-index: 2;
        }
        header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4em;
            margin-bottom: 20px;
            animation: fadeInDown 1s ease forwards;
        }
        header p {
            font-size: 1.5em;
            margin-bottom: 40px;
            animation: fadeInUp 1s ease forwards;
            animation-delay: 0.5s;
        }
        header .btn {
            padding: 15px 35px;
            border: 2px solid #fff;
            background: transparent;
            color: #fff;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        header .btn:hover {
            background: #fff;
            color: #111;
        }

        
        @keyframes fadeInDown {
            0% { opacity:0; transform: translateY(-50px);}
            100% { opacity:1; transform: translateY(0);}
        }
        @keyframes fadeInUp {
            0% { opacity:0; transform: translateY(50px);}
            100% { opacity:1; transform: translateY(0);}
        }

        nav {
            position: fixed;
            top: 0; left: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background: rgba(0,0,0,0.7);
            z-index: 100;
        }
        nav h2 { font-family: 'Playfair Display', serif; font-size: 1.5em; }
        nav ul { list-style: none; display: flex; gap: 25px; }
        nav ul li { font-weight: 500; }
        nav ul li a:hover { color: #f5c518; }

        section {
            padding: 100px 50px;
            text-align: center;
        }

        #about { background: #222; }
        #about h2 { font-size: 3em; margin-bottom: 20px; color: #f5c518; }
        #about p { font-size: 1.2em; max-width: 800px; margin: 0 auto; }

        #menu { background: url('https://images.unsplash.com/photo-1600891964844-0d3d735a7c08?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8Z3VybWFuJTIwZm9vZHxlbnwwfHwwfHw%3D&ixlib=rb-4.0.3&q=80&w=1080') center/cover no-repeat; position: relative; }
        #menu::after {
            content: "";
            position: absolute;
            top:0; left:0;
            width:100%; height:100%;
            background: rgba(0,0,0,0.6);
        }
        #menu .menu-content { position: relative; z-index: 2; color: #fff; }
        #menu h2 { font-size: 3em; margin-bottom: 50px; }
        .menu-items { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; }
        .menu-item {
            background: rgba(255,255,255,0.05);
            padding: 20px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease, background 0.3s ease;
        }
        .menu-item:hover { transform: translateY(-10px); background: rgba(255,255,255,0.15); }
        .menu-item img { width: 100%; border-radius: 10px; margin-bottom: 15px; }

        
        #admin { background: #222; color: #fff; padding: 100px 50px; text-align: center; }
        #admin h2 { font-size: 3em; margin-bottom: 50px; color: #f5c518; }
        .admin-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
        }
        .admin-card {
            background: rgba(255,255,255,0.05);
            padding: 20px;
            border-radius: 15px;
            width: 250px;
            transition: transform 0.3s ease, background 0.3s ease;
        }
        .admin-card:hover {
            transform: translateY(-10px);
            background: rgba(255,255,255,0.15);
        }
        .admin-card img {
            width: 100%;
            border-radius: 50%;
            margin-bottom: 15px;
        }
        .admin-card h3 {
            margin-bottom: 5px;
            font-family: 'Playfair Display', serif;
            color: #f5c518;
        }
        .admin-card p {
            font-size: 1em;
            color: #ccc;
        }

       
        .parallax {
            background: url('https://images.unsplash.com/photo-1586190848861-99aa4a171e90?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8c2VydmljZSUyMGZpbmV8ZW58MHx8MHx8&ixlib=rb-4.0.3&q=80&w=1080') center/cover fixed no-repeat;
            height: 60vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2em;
            font-family: 'Playfair Display', serif;
            color: #fff;
        }

        footer {
            background: #111;
            text-align: center;
            padding: 30px;
            font-size: 0.9em;
            color: #777;
        }

        html { scroll-behavior: smooth; }
    </style>
</head>
<body>

    <nav>
        <h2>Majestic</h2>
        <ul>
            <li><a href="#about">About</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#admin">Administrators</a></li>
        </ul>
    </nav>

    <header>
        <div class="hero-content">
            <h1>Welcome to Majestic</h1>
            <p>Experience Luxury Dining Like Never Before</p>
            <a href="#menu" class="btn">Explore Menu</a>
        </div>
    </header>

    <section id="about">
        <h2>About Us</h2>
        <p>Majestic Luxury Restaurant offers an exquisite dining experience with world-class chefs and a luxurious ambiance. Every detail, from our hand-picked ingredients to the elegant decor, is designed to delight your senses.</p>
    </section>

    <section id="menu">
        <div class="menu-content">
            <h2>Our Signature Dishes</h2>
            <div class="menu-items">
                <div class="menu-item">
                    <img src="https://tse3.mm.bing.net/th/id/OIP.cORvno5UnUeb2dODijenDgHaLH?cb=ucfimg2&ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3" alt="Dish 1">
                    <h3>Truffle Risotto</h3>
                    <p>Creamy risotto infused with premium truffles and parmesan.</p>
                </div>
                <div class="menu-item">
                    <img src="https://tse1.mm.bing.net/th/id/OIP.UhLwQ8YqOqBcukJdDMmbGwHaNK?cb=ucfimg2&ucfimg=1&rs=1&pid=ImgDetMain&o=7&rm=3" alt="Dish 2">
                    <h3>Wagyu Steak</h3>
                    <p>Succulent wagyu beef, grilled to perfection with rosemary butter.</p>
                </div>
                <div class="menu-item">
                    <img src="https://png.pngtree.com/thumb_back/fw800/background/20241128/pngtree-fresh-seafood-platter-with-lobster-image_16508338.jpg" alt="Dish 3">
                    <h3>Seafood Platter</h3>
                    <p>Fresh lobster, oysters, and shrimp served on a bed of ice.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="admin">
        <h2>Our Administrators</h2>
        <div class="admin-container">
            <div class="admin-card">
                <img src="https://assets-global.website-files.com/64acdf3ff8eba1208e118782/6514444305ea21ac7e27b0ac_JfvvyGSJKPKI99OPkPRWxleRDOWh7cpP5E-5dDObapA.png" alt="Admin 1">
                <h3>ALEXANDER</h3>
                <p>CEO</p>
            </div>
            <div class="admin-card">
                <img src="https://tse3.mm.bing.net/th/id/OIP.ump7Pvge9UhilRv37nFF1QAAAA?w=430&h=430&rs=1&pid=ImgDetMain&o=7&rm=3" alt="Admin 2">
                <h3>ROMASAY</h3>
                <p>Head Chef</p>
            </div>
            <div class="admin-card">
                <img src="https://i.pinimg.com/736x/03/af/9f/03af9fcff3550377a9c53395c4adbaeb.jpg" alt="Admin 3">
                <h3>BRUCE</h3>
                <p>MANAGER</p>
            </div>
        </div>
    </section>

    <div class="parallax">A Dining Experience Like No Other</div>

    <footer>
        &copy; 2025 Majestic Luxury Restaurant. All rights reserved.
    </footer>

</body>
</html>
```


## OUTPUT:
<img width="1835" height="915" alt="image" src="https://github.com/user-attachments/assets/ddb75270-f6d8-4064-9c48-39f0a1be15ef" />
<img width="1829" height="832" alt="image" src="https://github.com/user-attachments/assets/810f84cd-b9e0-462a-8ef3-a8ea044ba01f" />
<img width="1811" height="834" alt="image" src="https://github.com/user-attachments/assets/1b7e234f-56d3-4251-860f-6ad08e927e18" />
<img width="1831" height="906" alt="image" src="https://github.com/user-attachments/assets/ae5af3df-66ff-4965-b307-2742165e595f" />






## RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
