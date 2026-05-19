<!DOCTYPE html>
<html lang="sr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FK Vrbas - Sportski Klub</title>
    <style>
        {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #333;
        }

        p {
            color: white;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        nav {
            background: #1a1a2e;
            padding: 15px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav .logo {
            font-size: 24px;
            font-weight: bold;
            color: white;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        nav .logo span {
            color: #e94560;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 25px;
        }

        nav ul li a {
            color: white;
            font-size: 15px;
            font-weight: 500;
            transition: color 0.3s;
            padding: 5px 0;
        }

        nav ul li a:hover {
            color: #e94560;
        }

        .hamburger {
            display: none;
            font-size: 28px;
            color: white;
            cursor: pointer;
        }

        .hero {
            background: linear-gradient(rgba(26, 26, 46, 0.85), rgba(26, 26, 46, 0.7)),
                url('data:image/jpeg;base64,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') center/cover;
            min-height: 85vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 40px 20px;
        }

        .hero-content h1 {
            font-size: 52px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.3);
        }

        .hero-content h1 span {
            color: #e94560;
        }

        .hero-content p {
            font-size: 20px;
            max-width: 600px;
            margin: 0 auto 30px;
            line-height: 1.6;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 14px 32px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
        }

        .btn-primary {
            background: #e94560;
            color: white;
        }

        .btn-primary:hover {
            background: #d63851;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(233, 69, 96, 0.4);
        }

        .btn-outline {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-outline:hover {
            background: white;
            color: #1a1a2e;
            transform: translateY(-2px);
        }

        section {
            padding: 80px 40px;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 36px;
            color: #1a1a2e;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #666;
            font-size: 17px;
            max-width: 550px;
            margin: 0 auto;
        }

        .player-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .player-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid #eee;
            text-align: center;
            position: relative;
        }

        .player-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.12);
        }

        .player-card .number {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 32px;
            font-weight: 900;
            color: rgba(233, 69, 96, 0.15);
        }

        .player-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .player-card .info {
            padding: 15px;
        }

        .player-card h3 {
            font-size: 17px;
            color: #1a1a2e;
            margin-bottom: 3px;
        }

        .player-card .position {
            color: #e94560;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .player-card .stats {
            display: flex;
            justify-content: center;
            gap: 15px;
            font-size: 12px;
            color: #888;
            margin-top: 8px;
        }

        .player-card .stats span {
            font-weight: 600;
            color: #1a1a2e;
        }

        .matches-section {
            background: #f8f8fc;
        }

        .match-list {
            max-width: 700px;
            margin: 0 auto;
        }

        .match-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: white;
            padding: 18px 25px;
            border-radius: 10px;
            margin-bottom: 12px;
            box-shadow: 0 1px 5px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
            border-left: 4px solid #e94560;
        }

        .match-item:hover {
            transform: translateX(5px);
        }

        .match-item .date {
            font-size: 13px;
            color: #888;
            min-width: 90px;
        }

        .match-item .teams {
            font-weight: 600;
            font-size: 15px;
            color: #1a1a2e;
            flex: 1;
            text-align: center;
        }

        .match-item .teams .vs {
            color: #e94560;
            font-size: 12px;
            margin: 0 8px;
        }

        .match-item .venue {
            font-size: 13px;
            color: #888;
            min-width: 100px;
            text-align: right;
        }

        .match-item.past .teams .score {
            color: #e94560;
            font-weight: 700;
        }

        .table-section {
            background: white;
        }

        .standings {
            max-width: 700px;
            margin: 0 auto;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
        }

        .standings table {
            width: 100%;
            border-collapse: collapse;
            font-size: 14px;
        }

        .standings thead {
            background: #1a1a2e;
            color: white;
        }

        .standings th {
            padding: 14px 12px;
            text-align: left;
            font-weight: 600;
            font-size: 13px;
        }

        .standings th:first-child {
            padding-left: 20px;
        }

        .standings td {
            padding: 12px;
            border-bottom: 1px solid #eee;
            text-align: left;
        }

        .standings td:first-child {
            padding-left: 20px;
            font-weight: 700;
            color: #888;
            width: 30px;
        }

        .standings tr:hover {
            background: #f8f8fc;
        }

        .standings .team-name {
            font-weight: 600;
            color: #1a1a2e;
        }

        .standings .highlight {
            background: #fff5f5;
        }

        .standings .highlight td:first-child {
            color: #e94560;
        }

        .standings .pts {
            font-weight: 700;
            color: #1a1a2e;
        }

        .contact {
            background: #f8f8fc;
        }

        .contact-wrapper {
            max-width: 900px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 22px;
            color: #1a1a2e;
            margin-bottom: 20px;
        }

        .contact-info p {
            margin-bottom: 15px;
            color: #555;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .contact-form {
            background: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.08);
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px 15px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 15px;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: #1a1a2e;
        }

        .contact-form textarea {
            height: 120px;
            resize: vertical;
        }

        .contact-form button {
            width: 100%;
            padding: 14px;
            background: #e94560;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
        }

        .contact-form button:hover {
            background: #d63851;
        }

        footer {
            background: #1a1a2e;
            color: white;
            text-align: center;
            padding: 25px;
            font-size: 14px;
        }

        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #1a1a2e;
            color: white;
            padding: 16px 24px;
            border-radius: 10px;
            font-weight: 500;
            display: none;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
        }
    </style>
</head>

<body>

    <nav>
        <div class="logo">⚽ FK <span>Vrbas</span></div>
        <p>Uradjeno koristeci chatgpt kao alatku</p>
        <ul id="navMenu">
            <li><a href="#pocetna">Pocetna</a></li>
            <li><a href="#igraci">Igraci</a></li>
            <li><a href="#utakmice">Utakmice</a></li>
            <li><a href="#tabela">Tabela</a></li>
            <li><a href="#kontakt">Kontakt</a></li>
        </ul>
    </nav>

    <section class="hero" id="pocetna">
        <div class="hero-content">
            <h1>Vise od <span>kluba</span>, vise od <span>igre</span></h1>
            <p>Fudbalski klub Balkan — tradicija, strast i pobeda. Podrzite nas na svakom mecu!</p>
            <a href="#utakmice" class="btn btn-primary">Raspored utakmica</a>
            <a href="#igraci" class="btn btn-outline" style="margin-left:10px;">Upoznajte tim</a>
        </div>
    </section>


    <section id="igraci">
        <div class="section-title">
            <h2>Nasi igraci</h2>
            <p>Upoznajte tim koji nosi boje kluba sa ponosom</p>
        </div>
        <div class="player-cards">
            <div class="player-card">
                <div class="number">1</div>
                <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxMSEhUQEhIVFRUVFRUPFRUVFRAVFRUPFRUWFhUVFRUYHSggGBolHRUVITEhJSkrLi4uFx8zODMtNygtLisBCgoKDg0OGhAQGi0fIB0rLS0tLS0tLS0tLS0tLS0tLS0tLS0rLSstKy0tLS0tLS0tLTAtLS0rLS0tLS0tLSstLf/AABEIAMIBAwMBIgACEQEDEQH/xAAcAAAABwEBAAAAAAAAAAAAAAAAAQIDBAUGBwj/xABEEAACAgEBBAcFBAcHAwUBAAABAgADEQQFEiExBhMiQVFhkRQycYGhB7HB0SNCQ3KCkvAzUlNzorLhJDTSYmNktMIV/8QAGgEAAgMBAQAAAAAAAAAAAAAAAAECAwQFBv/EAC4RAAICAQQABQIFBQEAAAAAAAABAhEDBBIhMRMiMkHwUWEFFHGRsTOBwdHxQv/aAAwDAQACEQMRAD8AqFuAjF+sGJA1WrAlJqdec4l7ZTRO1+rzKS6w5j65aOropBsZBFhg3zJ/sMI6KICIrGHmTF0hivZDACuNhhFzJzaMxPsRgBC3jBvSZ7GYXsZgMYSG0kLpTDOmMBENTxkiuEdMcxQqMYxxjF5jW6YoCOxCsxsmObsQyGKwEFohnimWNsphYxRaANEEGDBhYBO0YZo8yxpkiAadolY41cIJAYsQZhgRt4gFGIIi1gIgAjEEViCAF3rZASjJltZTmHVpoORVvD0emlkmnEapXEfDyO4e4P2cRDacR0PEmyG4NyG/ZxFeziDrIOthYbkD2YQjpRD66KFsdhuQ2dKIk6UR/rIN+Kw3IjeyiJtoCqWPIDP/AAPOSt6PcFrNjLniQmVLZs3TjAHhxH8XlwHIlF26M5drBllUYxkZIU5PxPL8I5s0dY24TliM8AN0eQ7z8TH1uDLkkLg5wBgYyeHLw+6I2dQgdSM5HHOTxPwle5l+1Ei3RYjJ0s0+0NKrUdYoO9XjOe9O/wBCc+szrWyyMrRVJU6GRp4fs8WLIoPJWRsjtpYg6WTN+JLyNhaIR0sL2WSy8QbY7HZEfTRptPJb2yPZbGAw9UR1UU9sKuyAxt65GsEsyuZEvrgBFWORJWETABUEAMEANWDFAyOGgDSuijYSQ0UGkUPFhoqDYSd6JZo1vwi8KFsY4TEMYnehExhsYYMcUxnMUGjYODJAMPMZ6yDfkSOxj2YxtnWAVIh5Ak+PFj3Du4d/Pny5y72DsY3hrGbdReA4El38BjkBzJ+XiRRdIthslLnm9drWZByTTYqDJ+DL9TIuSTqzbh0uXZ4tcFZ7aqgqq7wODk5Az5jv9Y/obWZgTzJxzAHlwHD5TPI7Dvl90Z07PaGPug8eHAk/ceUHwSuzpuzNMHpKsMgpunHPBHa+k5vaSCVPAg4I8xN9dqzWi7p4JajP39kHO7/XlOf7WuC6m0bw4uzK/Z3SrHO+TjLcCAR458pGE+aLHp1kjd0w1JPH5fPwi0fJ3Rx58QDjsjJ4/DjF7J2c9yg2NupzHAHJPMrnkDx/KbTZXR2oJvLu+HbV2HMEdrBA444AcwJGeqintXLNWP8ACJeH4mR7U+jE5hEzTbe2Ivv1lFbALJlVBz4E4Aby/wCZmrUKnDAg+f8AXGThlU1wc7U6PLglUuvr7MZdpHd5IYRh0lqKEmR3tjDWR9640a5JMsQyxjlEMpHaa47GS6hwjd1ckVrDZYmBU21yM4ltbVIN1caAjiHD3YICNZ1cLqo318f0nbYKO84kB0Bacx0aRvA+hnUui2wq0UHdBPiRNpRoUx7g9BIbyzw+DzydMfCJ9nM9FNsyv/DX0ET/APyav8Nf5RDcLYeeBpzB7PPQ52LQf2SfyrGNTsjSopd66lUcywUAfMw3BsPP3s8BonX9bfpSD7NoWvO7vKy1BaznO7h7N1WHDPBuWPGL0WwaXRTqNNWLObKp3lHHIGQF3uGO715mjLq4Y15iLSRxwUE5wCcDeOATgeJ8BLBtlLXg2nOQG3VPDBAPFvn3es6ttfRoaHpRVRGUruooUbpUoeA8mM5Vo67SP0liEJmsqUO8roSCN7PIY8Jn/O74Nx4o6n4XpceeTUk3X6fu+UX2n2yGqKJw3U6vdGAAV7OR8ifXMz+1L23GweOMePPx8fhINqmsll7ySRnvJzHTYXIVQSTwCgZYnuAA5mUyc5yUlyjv41gwRljbSb9rKfaex2XdYIcOocbuG5jiM9+DkZ8pddGNFvdkhh8Tj1Am90fQ+1tPUllQBCkkErkFmZsZDZzxkvR9Gnq92ojzG6SfnkmaHnXR5WUIqTSkil23soU6F90ZYmsefGxR8uc5xr+q92xgDzHPI8OQOJ3mvZi2labUO42cggjkCR9QJV7X+ynT2WC6lhSwxkFOsUkcmHaBB5d55CX45VG0rHsjKSTlS+vf8HM9lWYQLnO72c4weGeBHcfKWtm1urr4c+Q7uPx/rAz89Nb9ml+cjUVeZ3HGflkxzTfZVvf2+qJHPFVYU/zuW/2zF4M3O6qz0svxDTLEouW7bXs/b+xgNXrtwI9gZjjOFUkb/MnePDw9J0fo70bqspD6tN9nAfqyWCVK3EKACMvjGWPeSBgRva32a2dW66e8NkcEuBXJ8N9B38vdl8+/X76MnxxjJ7t4ZB9ZVqPExxTSr7/OjkfiesWVKOOXlfaqufv9TN6/7MdMxzTfZXnJ3WC2KPAA8Dj4kzEbb6F6vTDeeosmMl6+2oPfnHaA8yBznX69Rk8P6xJ1FreBhi1816uTiPg83mqINM639oPR7SrX7SqCtjYodaxl7S53cVKDjrMkHBGDg5xneHPdt7IfTW2Uv2urYIXXO6Syh1Hk26fd8jz5zq4s8citE07KF64qpJJKRdVMuTHQaLAyySEjbLGKiOySJqKpYYjdiQEUxrhycaYI7AT1hkvZur3LFbuBBkGLAiZI730X2kjopBzwmwouGJ5i0O07qf7Oxl+B4ektk6aa0ftz6CVbGWbz0Z14g64TzyOnOt/xvoI4nTvWj9r9BDaxWjuW19s9ThEra21hlUXd90MAzEsQOALNjOTuEDjM1odv6a4hr71F4OOr1A6g1tkqOrpfGMnk3aJzzmP2LqrNoI1thrutqO71LfoXCYBS2m9BvK29vDByOz3d9nszRXW2rVqDqzX77pqq9DqaSqn3BdgnB5Z4mZNRK04t1Xz5/JXJ2bwhjx598iPrFAY54J7xwcAfHGD8pXdKtrJptNgEJvg1pgY3VCkkqOHJRwA8oWx9nodMtAcgNi1nrKrngMBDg4GABkceGec535eHheJNvl0v8sgmiHtDbYALgHcAzvsGWsr4q+CDMuvRe/Vm3V0msVtulVrsyLyCQ+HI7DADGSuM8+RM6Nptk6eo7y1KXxxtfNlpHna+WPrJa2Z5/IeXiY4Sxw/pr9/9dEo5ZQdwbTMLpPs1rYZtsZTvE/o2z+j7lbeBAbHHgTgkjiMGarYewqNED1KYLc2YlnI7hvHkPIR/a+reqrNe71jPXUu8CVDWWKmWAIJABJxkcpm6ekGpa86Zm05ZWdd4U6rdfDKicFdur7QuBLEg7ndxl+7Lkj2Qts1vWEnmR6SQrHGczN7a171kA2rUBWHd+pe79IzBVAUHguQ304iQtm7atFdurust3Kxa/Vmmta2UM4rFb43mOFXv5mVrE6sVM1eorDjDeoJUg9xDAgqfMSLtXaGqREGnVHbeVHNmSVrY4Ng7S727zIzkgHmeBrOiG1LNRpt+5laxbLKnKKVXKtlcKeI7LJLjruOD6x754nSfX7Am0zM6jZevRW6rVG3fOTvW2acrwOd0lbePHu3cYHOQ3badY3iNSx8Uuo1Cjz6sHTkjyE2LHh9f4T3iI63A8e+Q/OZE+SW5lB0f2zrbX3Ot4DBc20ujqBzHUuiMM4IDCywZ+EjbX6YWjstYdNvag6evfr32uVWClgOAUE72BxOAD34mgN2DlT8QeRPgR4/WZjU7EwzGsqQztaOuLM2ndmDE6ckHhvDe3SRx8gBNWm1UZSfiOvoPcWOydqvYupVEWy2mzcVd3qA7FFcISSePa97GOXPnMxrOlOotY1e0pWQSGr0FF2tvGOam0gIh7vd4Y5+Gl2evU1Cs2G1uLNY4RWZiSc9gADnw8JU7Y0VNrdZdZaEI/slvZKsjgWIrCkkkZySZVvxeI6XHt/zoVooW1DVsljMKDXvdXbtK5tVq96z3mp0iN2WPDn6S5p0KPpbXtrsXT1rbqC+o/wC51WtetkFxXnWo3sKDg5I4DHGJRr9DpiTTUit3lFBc/Gw8T8zIu1drXa/FFSFawQxGeLN3FvIeHz8MaIOUnwqX1+f7CNyfBkEqkhKZr9J0BuIyWA9ZY1dALO9x6TX4iNG0wZqkW0Te7T6HNWuQ2ZiNfUVJU8xLIysjJURMwjBCkyAgrBFQR0A1o9nW2/2aM3wEtK+i2qP7Fp17Y2ykq4KoAmmpoGOUzPK/YuWM8+XdGNUoyaj9JX0bNtd9xUOfCehtfpgc8JSV7MQNvYGYLKw8NHNNJ0E1b8d0D4mTh9nOqxxKj1nYdBUAJLur4Q8SQ9iODNsLV6Oxba/eU8xxBB5hh3gzoGytXdZWGerDY4hTn+uXxl5rtMCeMXs+oDgJTmgsi8xGWJMzG10o1SdXczLusHypUOrLwwAwI4glcY75J2datSJTWSEQboy2Tu893PgO8+WBNhZsuiztPTWzHgWZELepGZW6vYenHEUqOY4AjgefKY5aabjt3cFfgv6kanaAYqF47zbq+YGOP1HrJwcjPf4nz8BMnrtTXpHFmDurngOOM+GfMCWiaq5sAVEHu3vdHnwPGZ5YpYnUiqUXF0yfr9ILlAZ3TDLYGQqGDLy94Ed/hIWi2DXU/WV33qzYD4es9Ziyywl8oTktbYTjHvRZquP7Rc/uNj13oR0d3fYv8p/8o1kklSI2Sto7MquYO5fkqlVdlVgjb6hwOYyeUh1dHaVwM2soKkI197ICli2LhC27wZFPLxHImZTbnTJdLe+nZrGZN0ErWm72lVhgmwHkw7prB1y/rg/L/mTk8kErtJ9D5JlGmWt7GTIa1xY5ye04RawcHgOyijh4RdrNyYf8xhNUxGGbH8K/iIXtBHLUY8iqn6YlTdkWxyi45wQeHLI7vnzkXV6wKePDH6yhmX+NPeX44I+EsNLbvA/pWbHM9lR6YlZtzVVVVvZZkoo3izYxnkFUADeYngO7jK2m3VAmVx2k1jFa03j4qVx8yTgj5g+UmU7D1VvOyusfxO3zAwPrMl0Q6QCx238AliQO4L3AfAcJ07QasY5idKGkjFebs0xxRa5KqnoYOduosfyQLWp/3H6wtVsKmtcLWOAxvN2m/mbJmibXJ/eEz+3NrIoPaE0Rxxj0i2MIx9jlXSLSCu0gcjxmt6D6ZQgPeeMyO2dV1thbu7pbdF9sdUdxuXcZbJOhJ8nXtGgxJRUTK6fpRSo4vCt6Z0jvlVMnaLLayjBnG+lwHXcJsdudM0KkICTOd6242MXbmZdji7srnIiYgxFQTQVCMQQ4IxHatlbVRzwYH5zSUaoY5iedNPqnQ5VyvwJlrVtu/vtb1mV4zRuO07Q1YweImYfpDWLNwsAZzy/atpHGxvUyrstyc5jWMTmd82ftSvA7a+oku7a1WPfX1E4LpdUR+sfUyW2pOOZ9YbB7jom3uklacQwJ8BGNj9LaW9593yPCcy1N0Yqs4x7BOZ3ROlmnA/tBIG0ullGDh8zlVV8K6+LYG4mdKduG44X3Zo+hG3LtRUaTbg1AADhvtWeR48wMYP8AD4znepfMXs3WGmxbV5od4cAcjGCMHhggkfOLNhWSG0qktx2hVt77QB8Rn0j9dLn9YmNWMyHsPUgPEHqRkqeR3gfwjbtceepz8FAE4XRnOUfahst/b7CCO1XWTx5Nubv3BfWddXARTZZhioJA4nJAzwE5D9q2hK6iuwvnrayGz41kD7mX0nSeiurtt0lFvWoWepGbKKe1jB4jHeDN2o5w438+cE30iwNo/VR282IUfiY9XZcfdAX91Af9T8Ieb/8AEUfuIM+pgSkMe2zOfBm3h6ch6TEipj2jV97eZjZwxjIIB/eAAHyBMxn2uXkDT1dx6y0gHhld1V+PvPOg0DA+nynLvtcuzq607loU/NnfP3Ca9JG8q+xLH6jE6dypyDg+Imi0m17sY6xvWZtZO07zrNGlM0Xt7nm7epkbUXk8yTIK2wmskaJWGxi6jGMxxTGInpZEW2RgPEM8KCxNxkOySHMjWSaIsbgMEEkRYmHBBGAhRHQY4K4sJI7SzcR7MyMzSfakhWiFEbF1Wx83SChju9EMOyyJV425iQYATVthWWyODAxiAS7QIY2TFLGI7V0a1r3aOixeJCdWwYAhmrJQn4ndz85MGqX9Zd0/A4lZ9nCf9BXnkzWkeWLCOHpLzU8Dl1ZgeTqQcjzHfOBmVZJJfUol2c4+16ypq9O27kB7FJHcWVSB891vSXH2caqs7PqALZVrVPiP0rkD0I9Yj7ThQ2gJHdbWeXEcSM/XHzkL7JFr9mu7f7fOPjXX+Qml+bS/o/n8j/8AJsXwf1WP7zHHpHtLnwxHK2Tuy3yIHrJiDHDAyeQ7h5mYroqJOmX8vnOPfafdvbQsH9xak/0Bv/1Oy0D8vzM4f9oD52hqT/61X+WtF/CbdArm39izH2Z9ZIraRhHkM6xeS1eK3owpiwYhjqmLBjSmLBiAc3okmFmJJjADGMvHGjTRiEwjBBJCChwocYiyRRiAiRq7+EdDiSEJtldeMyweRxTxil0JMb0+kks6DMsNLRwljXp+E588zTDeZS/SESJ1Rmsv0uZV3aXjJxz8F2Jb3RVbhhFTLUaaN2aaNZ02bno3tsqWWBRJdtMYxL07MM47XR23oHVjQadfFC4+LWOfxly9J7mKE/NSfMdxkLoXV/0Ol/yFPqMyfd1i5C4deW63HHwPfOBl9cn92ZpdlF0p2A+p01tQWsuy5Q8lNikMm95bwEpeh/RnU6e25rq6q67FrICWBh1qZDHkMZ3voJrDq7OQRV+IP4xI09jnLHPz4ekSzNQcF0xXxQutgOA4/wBdwkqlO7v7/wAohKwvAYz3mPocDI+XnK1yRZJq+7hOBdMWzrtV/n2D0Yid+rXAAnAemH/far/Pt/3mdPQLllmMpxHEjUcUzpFw8piwY0DFqYAPKYoGNgxQMQxeYRMLMTmMQZMbaLJjbRgFBCgjEEYcKHARAFxkvTWyCEj1RxNHhMjZaho5mQRbD9og8TI2XlF3CTadRMyNTH6dWZjyaNsTRoHskC4xpdRwjT2TOtIy/BLZKyRkQOBIy2xTWwWikmdv85HZRG1Qle8sLjIdizbDC0jjZpqUrO79Dqj7BpQRnNCHHkRkfTEmnSODlML5ZJEf2XSK6aq/7lVaD+FQPwkliBxM85k5k39zM1yQOvccGrzCd27xgn9Udw8z4yW1hPIYHiZHxngvzPjKXIVDKL6DifyElVjJBxwikqA4R0LHFioCc/pPPfSt863VH/5F30sYT0QowJ566X07ut1Q/wDfsP8AMxb8Z1dAuWTgqKaLWJi1nRLhaxYjW9Ha1JiAWDFAxOIcQxWYWYIYWMQRMQxjjCNNGAUOJhwEFBBBGBFgzDt5xvenVTTRU1Q5vQsxOYIxDlZk+jT+Mr6mwZd6Fd6ZdRk2IsjBsQ9ZHKMmyXw0nCU20tGVORMumzqcqHJpcEfrIfWSMDDzOnSK7Hi8Sx4GN5gY8D8IqEeiNKWNdYfnuL2hyLboyY4d1fM+HONUF+qr5A7iZGDwO6MjnECxx4ek8Nl9TBj5Vm97gPD84sDuEj77eP0P5xQZvH7/AM5WBIHOLzGFDeJ+kcVD4n6flJIQ6DOG/aDpOr194Oe2RaCe8OoJx5A7w+U7gE8z9Jxn7X95dcCc4aisg/BrAQPT6zp6CXna+xOPZi25xaLmJ0qFzL/Q7L750pGvDj39ldptDnjiSjp8d0vqdCAJE2jVgcJBmjwF7FHdziBDdTzxHtJVvR7qVmTJHa6I7A90crqY90vtHs8Hukm/RBRymV6pXSKXkozVg8Yw0ma4jMhkzXB2rJJ2JgxAIckAnEEOCMCNqqypkUtNHrNOC0Ys2aMS/Hm8oTpuymRorMd1OlxykfEvjmsroUTLzo6DmZ/M1WwUxiYtfPyM0RdRNTVp8iV+1tKMGXNDDdlbtOzgZyNLJ7zJJ2zE2pgkRBEf1JG8YyZ6iD4JCI7pkLOqjgWZVB8CSAPvjZMm7Ar3tVp18b6R8usXMJuotgd81thB4Mf9J+8SEbW59Y3pX/4yRrGkBzgfT8p4eT5K7FWGwkgXOOAIwtPDj5pH0Y44ux+ePuxIit2h+6R6EfnHweMhELJlBz3t/M/5yUq+Z/mb85BoaTGfC5liFZT9MrGTRal0Z1ddNc6srupDKhIIIPA5HOcu+01Dv6ckkkpdxLFjj2m3dGT4AgeXAd065tnTdbVZT/iU2VfzoV/Gcm+0M5o09nhben8NgqvX6OZ0dG6/f/BODsotjAAZmm0lgAmG0+qKyx021CcDM6JtwyfSNmHGDIVuCOMqE2hw5xXto5SMpJG1RklY7YojWiXDYjOp1YxwjmzTkyrLLyHOyytmt2fWN2NbWcKpkrQ+7KvpA/YPwnLxwcpmKXZib9VvMfjFEysFnaPxksWTuRVI1R6JAMOMq0czGMPMEKFGBY1ntSc3KFBCPRAq9bKk84cEsh2IbPOajY0EEo1npJPo01R4Ss2meBggnO03qM7MpdzMTCgnoo9FgJcdDP8Av9N/mj7jBBIZ/wCnL9H/AAI7Xqvy++Q7uR+X3wQTx0uysZX3h8G+9ZITn8zCgkEMlVfhJB9z5j74IJYhMU/vL8vwnIung/6HT/5y/wD06YcE36T1fPuTx+5gTAnOCCdM2YOyUpkkGCCUz7OnP0CHMtdld0OCRy+g48+zW6M9mVfSH3DCgmXT+oz+5ztucfUwQTq+xePpHoIIEkCCCCAH/9k="
                    alt="">
                <div class="info">
                    <h3>Aleksandar Vidic</h3>
                    <div class="position">Golman</div>
                    <div class="stats">Godine: <span>28</span> | Utakmice: <span>120</span></div>
                </div>
            </div>
            <div class="player-card">
                <div class="number">5</div>
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ77q0RDbgp2dDZxuo9sjlVkFjJFp4406uuOg&s"
                    alt="">
                <div class="info">
                    <h3>Ognjen Djakonovic</h3>
                    <div class="position">Stoper</div>
                    <div class="stats">Godine: <span>25</span> | Golovi: <span>8</span></div>
                </div>
            </div>
            <div class="player-card">
                <div class="number">10</div>
                <img src="data:image/jpeg;base64,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"
                    alt="">
                <div class="info">
                    <h3>Mitar Bulatovic</h3>
                    <div class="position">Bocni igrac</div>
                    <div class="stats">Godine: <span>23</span> | Asistencije: <span>18</span></div>
                </div>
            </div>
            <div class="player-card">
                <div class="number">9</div>
                <img src="data:image/jpeg;base64,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"
                    alt="">
                <div class="info">
                    <h3>Isidor Saletic</h3>
                    <div class="position">Napadac</div>
                    <div class="stats">Godine: <span>22</span> | Golovi: <span>34</span></div>
                </div>
            </div>
        </div>
    </section>

    <section class="matches-section" id="utakmice">
        <div class="section-title">
            <h2>Raspored utakmica</h2>
            <p>Predstojeći i odigrani mecevi</p>
        </div>
        <div class="match-list">
            <div class="match-item past">
                <div class="date">10. mart 2025</div>
                <div class="teams">FK Vrbas <span class="score">3 : 1</span> FK Zvezda</div>
                <div class="venue">🏠 Kucni teren</div>
            </div>
            <div class="match-item past">
                <div class="date">17. mart 2025</div>
                <div class="teams">FK Partizan <span class="score">1 : 1</span> FK Vrbas</div>
                <div class="venue">✈️ Gostovanje</div>
            </div>
            <div class="match-item">
                <div class="date">24. mart 2025</div>
                <div class="teams">FK Vrbas <span class="vs">VS</span> FK Vojvodina</div>
                <div class="venue">🏠 Kucni teren</div>
            </div>
            <div class="match-item">
                <div class="date">31. mart 2025</div>
                <div class="teams">FK Radnicki <span class="vs">VS</span> FK Vrbas</div>
                <div class="venue">✈️ Gostovanje</div>
            </div>
            <div class="match-item">
                <div class="date">7. april 2025</div>
                <div class="teams">FK Vrbas <span class="vs">VS</span> FK Cukaricki</div>
                <div class="venue">🏠 Kucni teren</div>
            </div>
        </div>
    </section>

    <section class="table-section" id="tabela">
        <div class="section-title">
            <h2>Tabela</h2>
            <p>Trenutno stanje na tabeli prve lige</p>
        </div>
        <div class="standings">
            <table>
                <thead>
                    <tr>
                        <th>#</th>
                        <th>Klub</th>
                        <th>Od.</th>
                        <th>Pob.</th>
                        <th>Rem.</th>
                        <th>Por.</th>
                        <th>Gol raz.</th>
                        <th>Bod.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr class="highlight">
                        <td>1</td>
                        <td class="team-name">⚽ FK Vrbas</td>
                        <td>24</td>
                        <td>18</td>
                        <td>4</td>
                        <td>2</td>
                        <td>+32</td>
                        <td class="pts">58</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td class="team-name">FK Zvezda</td>
                        <td>24</td>
                        <td>17</td>
                        <td>3</td>
                        <td>4</td>
                        <td>+28</td>
                        <td class="pts">54</td>
                    </tr>
                    <tr>
                        <td>3</td>
                        <td class="team-name">FK Partizan</td>
                        <td>24</td>
                        <td>16</td>
                        <td>4</td>
                        <td>4</td>
                        <td>+24</td>
                        <td class="pts">52</td>
                    </tr>
                    <tr>
                        <td>4</td>
                        <td class="team-name">FK Vojvodina</td>
                        <td>24</td>
                        <td>14</td>
                        <td>5</td>
                        <td>5</td>
                        <td>+18</td>
                        <td class="pts">47</td>
                    </tr>
                    <tr>
                        <td>5</td>
                        <td class="team-name">FK Cukaricki</td>
                        <td>24</td>
                        <td>12</td>
                        <td>6</td>
                        <td>6</td>
                        <td>+10</td>
                        <td class="pts">42</td>
                    </tr>
                    <tr>
                        <td>6</td>
                        <td class="team-name">FK Radnicki</td>
                        <td>24</td>
                        <td>11</td>
                        <td>5</td>
                        <td>8</td>
                        <td>+5</td>
                        <td class="pts">38</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <section class="contact" id="kontakt">
        <div class="section-title">
            <h2>Kontaktirajte nas</h2>
            <p>Imate pitanje za klub? Javite nam se!</p>
        </div>
        <div class="contact-wrapper">
            <div class="contact-info">
                <h3>Informacije</h3>
                <p>📍 Stadion Vrbas , Vbas</p>
                <p>📞 021-345-678</p>
                <p>📧 info@fkbalkan.rs</p>
                <p>🎫 Ulaznice: ulaznice@fkvrbas.rs</p>
            </div>
            <form class="contact-form" onsubmit="submitForm(event)">
                <input type="text" placeholder="Vaše ime" required>
                <input type="email" placeholder="Vaš email" required>
                <textarea placeholder="Vaša poruka" required></textarea>
                <button type="submit">Posalji poruku</button>
            </form>
        </div>
    </section>

    <footer>
        <p>2025 FK Vrbas - Sportski Klub. Sva prava zadrzana.</p>
    </footer>

    <div class="toast" id="toast">✅ Poruka uspešno poslata!</div>


</body>

</html>
