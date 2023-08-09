<p align="center">
  <h1 align="center">🌈 Color Safe Map Markers📍️</h1>
  <p align="center">
    <br />
    <img src="https://github.com/Mary-Tyler-Moore/readme-gifs/blob/3abe93ee2b1304195dca07fe86832c5e404a5ffd/color-safe-markers.gif?raw=true" width="600px" />
    <br />
    <br />
    <a href="https://color-safe-markers.netlify.app/">View Demo</a>
    ·
    <a href="https://github.com/Mary-Tyler-Moore/color-safe-markers/issues">Report Bug</a>
    ·
    <a href="https://github.com/Mary-Tyler-Moore/color-safe-markers/issues">Request Feature</a>
  </p>
</p>

<br />

## 🌈 Color Safe Map Markers 📍

Have you ever wondered how our color perception affects our ability to distingush the difference between colored map markers? Would you like to learn more about the importance of web accessibility in design? Dive in and explore with me!

<br>

## 💾 Demo

📍 [Check out the live demo here!](https://color-safe-markers.netlify.app/) 🗺️

<br>

## 🌍 Web Accessibility

Web accessibility is a responsibility. Ensuring everyone can access and understand content is crucial. This project aligns with the **WCAG Guidelines**. Learn more [here](https://www.w3.org/WAI/standards-guidelines/wcag/).

<br>

## 💡 Inspiration

Our world is filled with colors. But not everyone sees them the same way. This project aims to educate and inspire by highlighting the importance of designing for everyone.

<br>

## 🌈 Color Blindness Types 📊

- **Protanopia** 🟥: 
  Individuals with protanopia lack the long-wavelength sensitive retinal cones, which means they are unable to perceive red light. As a result, reds appear as black or dark gray to them.
  
- **Protanomaly** 📛: 
  This is a reduced sensitivity to red light. People with protanomaly perceive red colors as being weaker than usual.
  
- **Deuteranopia** 🟩: 
  Individuals with deuteranopia lack the medium-wavelength retinal cones, making them unable to perceive green light. For them, greens may appear as beige or gray.
  
- **Deuteranomaly** 📗: 
  This is a reduced sensitivity to green light. People with deuteranomaly perceive green colors as being weaker than usual. This is the most common type of color blindness.
  
- **Tritanopia** 🟦: 
  Individuals with tritanopia lack the short-wavelength retinal cones, making them unable to perceive blue light. Blues may appear as green or even gray to them.
  
- **Tritanomaly** 📘: 
  This is a reduced sensitivity to blue light. Blues may appear greener than they actually are.
  
- **Achromatopsia** ⚪: 
  This is a very rare condition in which the person cannot perceive any color at all, seeing everything in shades of gray. This is due to the absence or nonfunctioning of all three types of color-sensing cone cells.
  
- **Achromatomaly** 📓: 
  This is an extremely rare form of color blindness where the person can only perceive slightly muted colors. It's a milder form of achromatopsia.
  
<br>
  
## Prevalence of Color Blindness in our Population 📊


| Type          | Description                           | Estimates: Total Population |
|---------------|---------------------------------------|-----------------------------|
| Protanopia    | Lack of red light perception          | 1.1%                        |
| Protanomaly   | Reduced sensitivity to red light      | 1.1%                        |
| Deuteranopia  | Lack of green light perception        | 3.1%                        |
| Deuteranomaly | Reduced sensitivity to green light    | 3.1%                        |
| Tritanopia    | Lack of blue light perception         | 0.2%                        |
| Tritanomaly   | Reduced sensitivity to blue light     | 0.2%                        |
| Achromatopsia | No color perception                   | 0.006%                      |
| Achromatomaly | Muted color perception                | 0.006%                      |

<br>

## 📚 Resources

- [SVG Filters](https://github.com/hadikachmar3/)
  
- [Designing Salesforce Maps for Color-Blind](https://www.salesforce.com/blog/how-we-designed-salesforce-maps-to-be-color-blind-friendly/)
  
- [The Salesforce Color System](https://medium.com/salesforce-ux/the-salesforce-color-system-c7c6b5b9c577)

<br>

## 🚀 Future Development

- [ ] Add Hex and RGB color code to README.md
- [ ] Integrate with Tailwind CSS for a sleeker design
- [ ] Enhance the UI for a smoother user experience
- [ ] Apply SVG Filters to the entire map, not just the markers

<br>

## 🧠 How It Works

**HTML, CSS, & JavaScript**: The holy trinity of web development. 🙌

1. **HTML**: We start with a canvas - our map.
    
    The HTML document includes a dropdown for selecting different colorblind filters 🎨 and a div with an id map 🗺️ to hold the map.
    
    The stylesheet link for Leaflet 🍃 and some custom styles for the map container are included in the `<head>` section 👤.
    
    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <title>Color Safe Markers</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
    <style>
        #map {
        height: 100dvh;
        }
    </style>
    </head>
    <body>
    <div id="container">
        <select id="filterDropdown">
            <!-- Options for different colorblind filters -->
        </select>
        <div id="map"></div>
    </div>
    </body>
    </html>

<br>

2. **CSS**: Using 🎭 SVG Filters we simulate different types of color blindness.

    A series of SVG filters are defined in a string and are later appended to the body o️f the html. These filters are used to simulate different types of colorblindness, such as Protanomaly, Protanopia, Deuteranomaly, etc 🌟.
    
    The filters will be applied to the map markers based on the user's selection from the dropdown 🎏.

    ```html
    <svg xmlns="http://www.w3.org/2000/svg" style="display:none;">
        <defs>
            <!-- Filters for protanomaly, protanopia, etc. -->
            <filter id="protanomaly">
                <feColorMatrix in="SourceGraphic"
                  type="matrix" 
                  values="0.817 0.183 0 0 0
                          0.333 0.667 0 0 0
                          0 0.125 0.875 0 0
                          0 0 0 1 0" />
            </filter>
            </filter>
            <filter id="protanopia">
                <feColorMatrix in="SourceGraphic"
                  type="matrix"
                  values="0.567 0.433 0 0 0
                          0.558 0.442 0 0 0
                          0 0.242 0.758 0 0 
                          0 0 0 1 0"  />
            </filter>
            <!-- Other filters... -->
        </defs>
      </svg>
    ```
    
<br>    

3. **JavaScript**: Our JS magic sprinkles 50 markers within the view area of the map. Every time the page loads, it's a brand new sight!


- **View Area Calculation**: JS calculates the total view area to ensure our markers are strategically placed.
  
- **Safe Area**: No marker left behind! We ensure that no markers are cut off from the screen edges. JS calculates a safe area within the view, accounting for marker size.

- **Intelligent Marker Placement**: JS ensures that our markers don't overlap or touch each other. Each marker respects personal space! 😂

<br>

### 🚫 Ensuring Non-Overlapping Markers 📍

To prevent markers from overlapping, we follow these steps:

1. **🔲 Setting Bounds**:
   When you initialize the map, it has a set boundary defined by the maximum and minimum latitudes and longitudes currently viewable on the screen.

   ```javascript
   // 1. Get the current bounds
   const currentBounds = map.getBounds();
   
2. **🌐 Generating Random Coordinates**:
   To place a marker, we generate a random latitude and longitude within the bounds of the map. However, it's essential to ensure that the generated position isn't too close to the edge where a marker might bleed out of view or overlap with markers near the boundary. This is achieved by setting a buffer.

   ```javascript
   function randomLatLngWithinBounds(bounds) {
       const southWest = bounds.getSouthWest();
       const northEast = bounds.getNorthEast();
   
       // Define a buffer based on an estimate for the marker size in terms of map coordinates
       const latBuffer = (northEast.lat - southWest.lat) * 0.08;  
       const lngBuffer = (northEast.lng - southWest.lng) * 0.08;
   
       const lat = Math.random() * (northEast.lat - southWest.lat - 2 * latBuffer) + southWest.lat + latBuffer;
       const lng = Math.random() * (northEast.lng - southWest.lng - 2 * lngBuffer) + southWest.lng + lngBuffer;
   
       return { lat, lng };
   }
   ```
   
<br>

3. **📏 Checking Proximity**:
   After generating a random coordinate, it's crucial to ensure that the new point isn't too close to any previously generated points. For this, we use a function called `isTooClose`.

   ```javascript
   function isTooClose(newPoint, existingPoints, minDistance = 0.012) {
       return existingPoints.some(point => {
           const latDiff = newPoint.lat - point.lat;
           const lngDiff = newPoint.lng - point.lng;
           return Math.sqrt(latDiff * latDiff + lngDiff * lngDiff) < minDistance;
       });
   }
   ```

   If the new point is too close to any existing point, we discard it and generate a new one. This loop continues until we find a suitable point that adheres to our non-overlapping criteria.
   
<br>   
   
4. **📍 Marker Icons**:
  
   Once we have a satisfactory coordinate, we use it to instantiate a marker and add it to the map. This process is repeated until we've placed the desired number of markers on the map.
   
   Create marker icons with different colors for both light and dark modes, and apply selected colorblind filters.

    ```JavaScript
    // Function to set marker icon based on color index and dark mode
    function setMarkerIcon(colorIndex, darkMode) {
        const colorArray = darkMode ? markerColorsDark : markerColors;
        const imageUrl = colorArray[colorIndex];

        // Create an SVG representation for the marker
        const svgString = `<svg xmlns="http://www.w3.org/2000/svg" width="27.75px" height="40px" viewBox="0 0 27.75 40">
            <image x="0" y="0" width="27.75px" height="40px" xlink:href="${imageUrl}" class="colorblind-marker"/>
        </svg>`;

        return L.divIcon({
            className: 'svg-marker-icon',
            html: svgString,
            iconSize: [27.75, 40],
            iconAnchor: [13.875, 40],
            popupAnchor: [1, -34]
        });
    }
    ```
<br>    

5. **📍 Random Marker Genertion 🎲**:
   Once we have a satisfactory coordinate, we use it to instantiate a marker and add it to the map. This process is repeated until we've placed the desired number of markers on the map.

   ```javascript
   // Generate random markers and store their color indices
    const randomMarkers = [];
    const existingCoords = [];

    for (let i = 0; i < 50; i++) {
        let coords = randomLatLngWithinBounds(currentBounds);

        // Check if the generated coordinates are too close to any of the previously generated coordinates
        while (isTooClose(coords, existingCoords)) {
            coords = randomLatLngWithinBounds(currentBounds);
        }

        existingCoords.push(coords);

        const colorIndex = Math.floor(Math.random() * markerColors.length);
        randomMarkers.push({ ...coords, colorIndex });
    }
   ```

    By following this approach, we ensure that our markers are spread out across the map, providing a user-friendly experience. 🤩👌
    
<br>    
    
6. 🎉 **Event Listeners 🎧**:
   Listen to events for switching marker icons and applying filters.

   ```javascript
    // Event listener to switch marker icons when the layer changes
    map.on('baselayerchange', function (eventLayer) {
       const isDarkMode = eventLayer.name === "Dark Map";
      // Switch marker icons and apply selected filter
    });

    // Event listener for the dropdown
    document.getElementById('filterDropdown').addEventListener('change', function() {
        const selectedFilter = this.value;
        applyColorblindFilter(selectedFilter);
    });

   ```
   
<br>   
   
5. 🗺 **Layer Control 🕹️**:
   Listen to events for switching marker icons and applying filters.

   ```javascript
    // Create the layer control
    const baseLayers = {
        "Bright Map": brightLayer,
        "Dark Map": landMap
    };

    L.control.layers(baseLayers).addTo(map);


   ```

<br>   
   
## 📜 Summary 

This project is a celebration of colors and perspectives! 🎉 Whether you're a map enthusiast, accessibility advocate, or just someone who loves colors, this project is for you! 🎈

<br>


## Contributing 🤝

Feel free to fork, star ⭐,    or contribute to this project. All ideas are welcome! 🎉


<br>

## License 📄

<br>

MIT License. Feel free to use and share! 🎁

You dont need my permission to use the icons or color palletes in your project, and you don't have to give me credit, but it would be much appreciated! 

<br>

## Websites Using 🌈 Color Safe Map Markers📍

Please let me know if you end up using the map markers or color pallete in your project. I'll list all of the projects below.

<br>

🌈 [Color Safe Map Markers📍- https://color-safe-markers.netlify.app/](https://color-safe-markers.netlify.app/)️

