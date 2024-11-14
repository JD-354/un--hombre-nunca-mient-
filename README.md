<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <lik rel="./stylesheet" href="./html.Css"></lik>
</head>
<body>
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(45deg, #1a1a1a, #2c3e50);
        }

        .card {
            position: relative;
            width: 750px;
            height: 450px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 25px 45px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            align-items: center;
            transition: 0.5s;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 35px 65px rgba(0, 0, 0, 0.3);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at right top, 
                rgba(1, 67, 255, 0.3),
                transparent 40%);
            pointer-events: none;
        }

        .left-section {
            width: 40%;
            height: 100%;
            background: rgba(255, 255, 255, 0.1);
            padding: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border-right: 1px solid rgba(255, 255, 255, 0.1);
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 3px solid rgba(255, 255, 255, 0.2);
            overflow: hidden;
            margin-bottom: 20px;
            transition: 0.5s;
        }

        .profile-img:hover {
            transform: scale(1.1);
            border-color: #0088ff;
        }

        .profile-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .right-section {
            width: 60%;
            padding: 40px;
            color: white;
        }

        .name {
            font-size: 2.5em;
            margin-bottom: 10px;
            font-weight: 700;
