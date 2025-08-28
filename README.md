<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>People for People - Community Support Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables */
        :root {
            --primary-color: #2575fc;
            --secondary-color: #6a11cb;
            --accent-color: #ff4757;
            --text-color: #333;
            --light-gray: #f5f5f5;
            --medium-gray: #ddd;
            --dark-gray: #777;
            --white: #fff;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--secondary-color) 0%, var(--primary-color) 100%);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            width: 100%;
        }
        
        /* Header Styles */
        header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px
