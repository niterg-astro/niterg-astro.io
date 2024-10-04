<!DOCTYPE html>
<html lang="en">
    <head>
        <meta name="description" content="Find the Nakshatra based on Zodiac sign and it's degree, Also find yourself resonatiing sloka from Vishnu Sahasranamam">
        <meta name="keywords" content="Nakshatra, Pada, Vishnu Sahasranamam">
        <meta name="author" content="Niterg">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta property="og:image" content="Krishna.jpeg">
        <title>Nakshatra and Zodiac Finder</title>
        <!-- Latest compiled and minified CSS -->
        <link
            href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
            integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
            crossorigin="anonymous"
        >
        <link rel="stylesheet" href="./Astrology/Assets/CSS/main.css">
        <link rel="stylesheet" href="./Astrology/Assets/CSS/fonts.css">
        <link rel="stylesheet" href="./Astrology/Assets/Icons/bootstrap-icons.css">
    </head>
    <body>
        <div class="navbar-c ">
            <a href="#" onclick="openTab('nakshatra-tab')">Nakshatra</a>
            <a href="#" onclick="openTab('zodiac-tab')">Zodiac Sign</a>
            <a href="#" onclick="openTab('show-nakshatra-tab')">Show Nakshatra</a>
            <a href="#" onclick="openTab('gun-milan-tab')">Guna Milan</a>
        </div>
        <div class="business">
            <div class="app-brand">
                <!-- Nakshatra Tab -->
                <div class="tab-content p-2 mt-2 active">
                    <h2>Click on any of the tab above to check out minute features</h2>
                    What you can find here
                    <ul>
                        <li>
                            Nakshatra Picker showing degree
                        </li>
                        <li>
                            Finding Nakshatra from Zodiac Sign
                        </li>
                        <li>
                            To show the Name of Nakshatra from Zodiac Sign and Degree
                            <ul>
                                <li>
                                    Also shows corresponding
                                    <b>Vishnu Sahasranamam Sloka</b>
                                </li>
                            </ul>
                        </li>
                    </ul>
                    <div id="contact"></div>
                </div>
                <div id="nakshatra-tab" class="tab-content p-2 mt-3 row">
                    <div class="col-sm col-lg-5">
                        <h2>
                            <i class="bi bi-bezier p-2 "></i>
                            Nakshatra / नक्षत्र
                        </h2>
                        <label for="nakshatra">Choose a Nakshatra:</label>
                        <select id="nakshatra" class="form-control">
                            <option value="">-- Select Nakshatra --</option>
                        </select>
                        <br>
                        <button onclick="showDegreeFromNakshatra()" class="form-control">Show Degree and Zodiac</button>
                    </div>
                    <div class="col-md col-lg">
                        <div id="nakshatra-result" class="result"></div>
                    </div>
                </div>
                <!-- Zodiac Sign Tab -->
                <div id="zodiac-tab" class="tab-content p-2 mt-3 row">
                    <div class="col-sm col-lg-5">
                        <h2>
                            <i class="bi bi-bezier2 p-2 "></i>
                            Zodiac Sign / राशी चिन्ह
                        </h2>
                        <label for="zodiac-list">Choose a Zodiac Sign:</label>
                        <select id="zodiac-list" class="form-control">
                            <option value="">-- Select Zodiac Sign --</option>
                            <option value="Aries">Aries / मेष</option>
                            <option value="Taurus">Taurus / वृष</option>
                            <option value="Gemini">Gemini / मिथुन</option>
                            <option value="Cancer">Cancer / कर्कट</option>
                            <option value="Leo">Leo / सिंह</option>
                            <option value="Virgo">Virgo / कन्या</option>
                            <option value="Libra">Libra / तुला</option>
                            <option value="Scorpio">Scorpio / वृश्चिक</option>
                            <option value="Sagittarius">Sagittarius / धनु</option>
                            <option value="Capricorn">Capricorn / मकर</option>
                            <option value="Aquarius">Aquarius / कुम्भ</option>
                            <option value="Pisces">Pisces / मीन</option>
                        </select>
                        <br>
                        <button onclick="showNakshatraFromZodiac()" class="form-control">Show Nakshatras and Degrees</button>
                    </div>
                    <div class="col-sm col-lg">
                        <div id="zodiac-result" class="result row"></div>
                    </div>
                </div>
                <!-- Show Nakshatra Tab -->
                <div id="show-nakshatra-tab" class="tab-content p-2 mt-2 mx-2 ">
                    <div class="row">
                        <!-- Column for zodiac selection and degree input (4 columns on large screens, 12 on small screens) -->
                        <div class="col-sm-12 col-lg-6">
                            <h2>
                                <i class="bi bi-stars p-2 "></i>
                                Show Nakshatra / नक्षत्र
                            </h2>
                            <label for="zodiac">Choose a Zodiac Sign:</label>
                            <select id="zodiac" class="form-control">
                                <option value=" ">-- Select Zodiac Sign --</option>
                                <option value="Aries">Aries / मेष</option>
                                <option value="Taurus">Taurus / वृष</option>
                                <option value="Gemini">Gemini / मिथुन</option>
                                <option value="Cancer">Cancer / कर्कट</option>
                                <option value="Leo">Leo / सिंह</option>
                                <option value="Virgo">Virgo / कन्या</option>
                                <option value="Libra">Libra / तुला</option>
                                <option value="Scorpio">Scorpio / वृश्चिक</option>
                                <option value="Sagittarius">Sagittarius / धनु</option>
                                <option value="Capricorn">Capricorn / मकर</option>
                                <option value="Aquarius">Aquarius / कुम्भ</option>
                                <option value="Pisces">Pisces / मीन</option>
                            </select>
                            <br>
                            <label for="degree">Enter Degree (0° - 30°):</label>
                            <input
                                type="number"
                                id="degree"
                                min="0"
                                max="30"
                                placeholder="Enter degree"
                                class="form-control"
                                value=""
                            >
                            <br>
                            <button onclick="findNakshatra()" class="form-control">Find Nakshatra</button>
                        </div>
                        <!-- Column for result (8 columns on large screens, 12 on small screens) -->
                        <div class="col-sm-12 col-lg-5 justify-items-center p-2 m-2 ">
                            <div id="nakshatra-result-pada" class="result"></div>
                        </div>
                    </div>
                    <br>
                    <!-- Row for translation (full-width across all screen sizes) -->
                    <div id="sloka-translation" class="result"></div>
                </div>
                <!-- Show Gun Milan Tab -->
                <!-- Zodiac Sign Tab -->
                <div id="gun-milan-tab" class="tab-content p-2 mt-3 ">
                    <h2>Gun Milan Table Soon to be available</h2>
                    Check out our other Platforms to contact us till then
                    <div class="row">
                        <!-- Telegram  -->
                        <div class="col-lg-3 col-md-4 col-sm-6 col-12">
                            <div class="card mb-3">
                                <div class="row g-3">
                                    <div class="col-sm-12">
                                        <img src="./Astrology/Assets/Images/Krishna.jpeg" class="img-fluid contact-logo  rounded-2" alt="Krishna">
                                    </div>
                                    <div class="col-sm-12">
                                        <div class="align-items-center"></div>
                                        <div class="card-body">
                                            <div class="align-items-center justify-items-center">
                                                <h2>
                                                    <i class="bi bi-telegram p-2 "></i>
                                                    Telegram
                                                </h2>
                                                <br>
                                                <h5>Nitya Chat (Astrology)</h5>
                                                <br>
                                                <div class="card">
                                                    <a href="https://t.me/nitya_chat" target="_blank" class="btn btn-success">
                                                        <i class="bi bi-telegram p-2 "></i>
                                                        Join Channel
                                                    </a>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <!-- Discord  -->
                        <div class="col-lg-3 col-md-4 col-sm-6 col-12">
                            <div class="card mb-3">
                                <div class="row g-3">
                                    <div class="col-sm-12">
                                        <img src="./Astrology/Assets/Images/Narayana.jpg" class="img-fluid contact-logo  rounded-2" alt="Krishna">
                                    </div>
                                    <div class="col-sm-12">
                                        <div class="card-body">
                                            <div class="align-items-center">
                                                <h2>
                                                    <i class="bi bi-discord p-2"></i>
                                                    Discord
                                                </h2>
                                                <br>
                                                <h5>Sanatan Satsang</h5>
                                                <br>
                                                <div class="card">
                                                    <a href="https://discord.gg/fuNgs3a5CV" target="_blank" class="btn btn-success">
                                                        <i class="bi bi-discord p-2"></i>
                                                        Join Server
                                                    </a>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <script src="./Astrology/Assets/JS/main.js"></script>
    </body>
</html>
