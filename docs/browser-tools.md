---
id: browser-tools
title: Tracking a Satellite with browser tools
sidebar_label: Tracking a Satellite with browser tools
---

## Parts required:

- Internet connection
- Desktop or laptop
- Smartphone

## Planning

### Step 1: Determine when the ISS will be visible from your location

- Input your location in Heavens Above
  - Go to [Heavens-Above.com](https://www.heavens-above.com/) (best viewed on desktop).
  - Confirm that Heavens-Above knows your observing location (which allows it to tell you exactly when and where to look), by looking at the “location” noted in the top-right corner of the page. If this location doesn’t match where you’ll be observing from, click the [latitude/longitude](https://www.heavens-above.com/SelectLocation.aspx) to input your location. From here you can search for your location, or input your lat/long from [Google Maps](https://support.google.com/maps/answer/18539?co=GENIE.Platform%3DDesktop&hl=en)

![Heavens Above location settings](https://trusat-learn-assets.s3.amazonaws.com/heavens-above-1.jpg)

- Click “update” at the bottom of the page to set your location.

## Find the best time to observe

- Check the upcoming ISS passes [here](https://www.heavens-above.com/PassSummary.aspx?satid=25544&lat=0&lng=0&loc=Unspecified&alt=0&tz=UCT). Each row in the table is an opportunity to see it. Scan the dates in the table to find a day and time when you’ll be available to observe.

![Heavens Above visible passes table](https://trusat-learn-assets.s3.amazonaws.com/heavens-above-2.jpg)

- Here’s a guide to the columns:
  - Brightness: Lower magnitudes indicates a brighter object
  - Start: The time, compass direction, and altitude to see the ISS when it first becomes visible. For most satellites, this will be ~10° above the horizon.
  - Highest point: As the satellite passes by you, there will be a single point in its arc that’s highest above the horizon. Given clear weather, this will usually be when the satellite is most visible, as the light passes to your eye through less of the Earth’s atmosphere
  - End: The point at which the satellite is no longer visible. Sometimes this is when the satellite drops back behind the horizon. Other times it’s when the satellite passes into Earth’s shadow, where it can no longer reflect the direct shine of sunlight.
- If the ISS doesn’t seem to be visible at a convenient or near-term time for your location, try picking another satellite from Heavens-Above’s daily [list of brightest satellites](https://www.heavens-above.com/AllSats.aspx).
- Make sure the weather will be clear enough to observe, with as few clouds as possible.

### Step 2: Plan your observation with a star chart

#### Load the star chart

- When you’ve decided on which ISS pass you plan to observe, click on the “star chart” link for the respective pass.

![Heavens Above start chart](https://trusat-learn-assets.s3.amazonaws.com/heavens-above-3.jpg)

- On the next page, scroll down to see the star chart you can use to familiarize yourself with the arc of the ISS’s path
- The ISS appears as an arcing string of light-grey spheres traveling from the edge of the star chart (the horizon) until crossing into the Earth’s shadow.
- If you want to enlarge the image, change the “output size” dropdown to a higher number (located in the green “Simulation” box above the chart and to the left).

#### Find your “finish line”

- A basic satellite observation only needs two pieces of info:
  - Your location (which you already have)
  - The time at which you observe the satellite cross an imaginary line between two known stars. We’ll call this a “finish line.”
- To find your finish line, look at the constellations near the ISS’s path and take note of the brightest stars (indicated by larger grey dots) that the ISS path passes between.
- Pick two stars can serve as reference points between which you can imagine drawing your finish line. Once you’re outside, you’ll need to note the exact time when the ISS crosses this line.

![Heavens Above "finish line"](https://trusat-learn-assets.s3.amazonaws.com/heavens-above-4.jpg)

- To find the name of the stars, check the label that appears above the star chart when you hover the mouse over the stars’ dots.

## Observing

### Step 3: Watch the skies

- When it’s about time for the satellite pass, position yourself outside with enough time to get oriented with the stars. Bring a coat if it’s cold!
- If you’ve been viewing your star chart on a desktop computer, and want to take the image with you outside, you can text yourself the link to the image, or print it out on paper.
- There are also mobile apps that can help you read the stars and find satellites:
  - SkyView Lite - Free - [Android](https://play.google.com/store/apps/details?id=com.t11.skyviewfree&hl=en_US), [iOS](https://apps.apple.com/us/app/skyview-lite/id413936865)
  - Orbitrack - \$4.99 - [Android](https://play.google.com/store/apps/details?id=com.southernstars.orbitrack), [iOS](https://apps.apple.com/us/app/orbitrack/id1092984911)

![Orbitrack app](https://trusat-learn-assets.s3.amazonaws.com/orbit-track.jpg)(Orbitrack app)

- Find the reference stars you identified in the star map to imagine your “finish line” spanning between. It may turn out that the stars you chose from the star map are not actually visible. In this case, use the star map or one of the mobile apps above to help identify the names of the stars that are visible and suitable for your finish line. If the ISS isn’t predicted to pass between any two visible stars, but other stars are still visible, you can choose two stars to draw your finish line between and extend it beyond
- Now just keep an eye on your reference stars at the times the ISS is predicted to pass by, and be ready to record the exact time. The

Note: If you have a camera suitable for photographing the satellite, skip ahead to the photography section at the bottom of this doc, then move on to Step 6.

### Step 4: Record the crossing time

When the ISS crosses the finish line, note the exact time. If you don’t have a phone that displays the time with exact seconds (most don’t), try one of these methods:

1. Freeze Time app [(Android)](https://play.google.com/store/apps/details?id=com.sandcreeksoftware.raceclock&hl=en_US)
   This app functions like a stopwatch, but shows the precise time.

![Freeze Time app](https://trusat-learn-assets.s3.amazonaws.com/freeze-time.jpg)

2. A digital (or physical) stopwatch. Start the stopwatch when you want to record your time, but don’t hit stop yet. Look at a clock and wait until the clock turns to the next minute. Stop the stopwatch just as the minute changes, then subtract the time on the stopwatch from the time on the clock to get the exact time of observation.

3. Take a throw-away photo or screenshot with your phone at the point when you want to record an observation. Don’t worry about capturing a real image with the photo. The photo will contain meta-data with the exact time, which you can view on a computer. If photo’s meta-data doesn’t seem to show time down to the second, upload the photo [here](http://exif.regex.info/exif.cgi).

## Processing

### Step 5: Convert your data into coordinates

Our goal now is to determine the exact coordinates for the position in the sky where you observed the satellite, using [right ascension and declination](https://www.skyandtelescope.com/astronomy-resources/right-ascension-declination-celestial-coordinates/)—which are like latitude and longitude for the skies.

#### Save your star chart

- Visit [CalSky.com](https://www.calsky.com/) on a desktop computer.
- Similar to Heavens Above, enter the coordinates where you observed from, in the top-right corner of the site.

![Calsky](https://trusat-learn-assets.s3.amazonaws.com/calsky-1.jpg)

- Visit their [ISS page](https://www.calsky.com/cs.cgi/Satellites/4?) (or [search here](https://www.calsky.com/cs.cgi/Satellites/1?) if you’re tracking a different satellite)
- Enter the day and time when you made the observation and click the circular, blue-green “go” button on the right.

![ISS page](https://trusat-learn-assets.s3.amazonaws.com/iss-page-1.jpg)

- After the page refreshes, scroll down to see a list of passes, find the pass that matches your observation, and click “star chart.” The ISS should appear as an arc across the chart.

![ISS page](https://trusat-learn-assets.s3.amazonaws.com/iss-page-2.jpg)

#### Find your reference stars

- When you hover your mouse over stars, it will display their name above the chart. Find the reference stars you used to draw your imaginary finish line.
- If the arc representing the ISS does not cross this line in the chart, you may need to “rewind” or “fast-forward” time by changing the time settings by a few minutes back or forward, which will update the chart. Adjust the time until the arc of the ISS passes between your reference stars.

![Reference stars](https://trusat-learn-assets.s3.amazonaws.com/iss-page-3.jpg)

#### Draw your finish line

- Save or screenshot the chart. In the next few steps, we’ll explain how to draw your finish line within Google Docs, but feel free to use a drawing app of your choice
- Navigate here, to the very bottom of this Google Doc
- At the top menu bar of this Google Doc, click the “Insert” menu, select “Drawing”, and click “+New”
- In the drawing canvas pop-up, click the image icon (![image icon](https://trusat-learn-assets.s3.amazonaws.com/image-icon.jpg)) and upload your star chart.
- Now click the line icon (![line icon](https://trusat-learn-assets.s3.amazonaws.com/line-icon.jpg)) and drag a finish line between your two reference stars.
- Click the line-color icon (![line-color icon](https://trusat-learn-assets.s3.amazonaws.com/line-color-icon.jpg)) to change the line color to yellow, so that it’s visible against the black background.
- Click “Save and close.”

![finish line](https://trusat-learn-assets.s3.amazonaws.com/finish+line.jpg)

#### Find the crossing point in CalSky

- Now you can use the star chart in this doc as a reference image to help you navigate the interactive star chart on CalSky
- With the reference image and CalSky chart visible side-by-side, use your mouse in the interactive chart to hover over the point where the ISS’s arc passes through the finish line. Write down the “R.A.” and “Dec” that appears above the chart. This pair of numbers for right ascension and declination is the last ingredient you’ll need to submit your observation.

#### Some tips for the above process

- To ensure as much accuracy as possible with the above method, you’ll need to fiddle with the field of view for CalSky’s star chart. Ideally, the reference stars and crossing point of the ISS’s arc span as much of the image as possible (rather than taking up only a small section of the image). This ensures the ISS’s arc displays at a large enough scale to return more precise coordinates when you mouse over the arc.
- To create these ideal conditions in the image, first change the “output size” dropdown to “1080” (located in the green “Simulation” box above the chart and to the left).
- You may also need to adjust the “Field of view (width)” dropdown under the “Pointing” green box.
- Adjusting the “Select interval” dropdown to around 1 second will create more snapshots of the ISS on its arc to hover over with the mouse (dropdown located with the time settings at the top of the page)

### Step 6: Submit your data

Now you have all of the information necessary to submit your observation to TruSat.

- Go to [TruSat.org/submit/single](https://www.trusat.org/submit/single)

![TruSat submission form](https://trusat-learn-assets.s3.amazonaws.com/trusat-submit.jpg)

- In the first field for “Station location”, you’ll need to follow the link to save your observation location with TruSat
- Fill out the rest form and hit “submit” to contribute your data to the global record of satellite behavior!
