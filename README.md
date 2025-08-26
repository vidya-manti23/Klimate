 # 🌦️ Weather App - Klimate

A simple and modern Weather App built using **HTML** and **CSS** with a clean Glassmorphism UI design.  
This project currently focuses on the **UI structure and styling**, showcasing frosted-glass effects, a search bar, and layout for weather details.  

 ✨ Features
- Glassmorphism design with blurred background  
- Responsive and clean UI  
- Sections for temperature, sunrise/sunset, forecast, and metrics  

 🛠️ Technologies
- **HTML5** – structure  
- **CSS3** – styling and glassmorphism effects  and 'flexbox styling'

👨‍💻 Created as a practice project for modern UI + weather app design.



# Workflow

dateFormat(ts)        -> UNIX → local datetime

fetchAQIData(lat,lon) -> call AirPollution API
                         update AQI (NO2,O3,CO,SO2)

nextFiveDays(lat,lon) -> call 5-day/3h forecast API
                         loop list → 1 entry/day
                         update days[], icons[], temps[]

todayTemps(lat,lon)   -> call 5-day/3h forecast API
                         pick next 4 slots
                         if missing → placeholder

fetchData()           -> get cityName (input)
                         call CurrentWeather API
                         update UI (temp, desc, hum, pres, feel, vis)
                         format sunrise/sunset
                         call → fetchAQIData(), nextFiveDays(), todayTemps()

# Weather app syntax cheatsheet

- for every link, we give relation and hyper reference
- `<link rel="stylesheet" href="index.css">`

- main content parent div divided into 2 divs: left and right, top lo search bar
- `<input type="text" class="inputfield" placeholder="Search city">`
- in left div, leftchild is common class
- `<h6 class="m-0" id="cityname">City name</h6> `// if you want to change the value just give it an id //
- `$("#no2value")[0].innerText = list.no2;` // changing that innertext using id
- `<hr class="line">` // for line to appear
- d-flex → by default row wise
- align-items-center → we can keep text in exact center, superscript, subscript la kakunda
- justify-content-between → space between 2 elements
- `&deg;` → degree symbol
- fetch from api, convert to json, then list them and change using jquery
- let res = await fetch(`https://api.openweathermap...`);
- let formattedData = await res.json();
- let list = formattedData.list[0].components;
- `$("#no2value")[0].innerText = list.no2;`



