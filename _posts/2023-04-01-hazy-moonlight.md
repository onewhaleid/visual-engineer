---
id: 5
title: 'Hazy moonlight'
date: '2023-04-01T06:40:17+01:00'
author: dan
layout: post
guid: 'https://visualengineer.org/?p=5'
permalink: /2023/04/01/hazy-moonlight/
image: https://www.visualengineer.org/assets/2023/04/weather-feature.png
description: Weather is everything that gets in between you and the sun.
---

Growing up on the east coast of Australia, the weather was generally pretty agreeable. The forecast year-round mostly looked like this:

<figure>
<img class="w-300" src="/assets/2023/04/1.svg">
<figcaption>
Ok, sometimes it rained. But only during La Niña.
</figcaption>
</figure>

When I moved from sunny Australia to Germany with my family, I suddenly needed a weather app. It’s nice to be prepared when things can deteriorate so quickly. One recent winter morning my wife held up her phone to show me the “current weather” symbol. It looked like this:

<figure>
<img class="w-300" src="/assets/2023/04/24.svg">
<figcaption>
Current weather: I’m not sure, but definitely nothing good.
</figcaption>
</figure>

The weather provider we use has a collection of weather symbols on their website[^1], numbered from 1 to 44. I downloaded the full list of symbols to investigate the full gamut of weather on offer:

|    | 00          | 01          | 02          | 03          | 04          | 05          | 06          | 07          | 08          | 09          |
|----|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| 00 |             | ![][1.svg]  | ![][2.svg]  | ![][3.svg]  | ![][4.svg]  | ![][5.svg]  | ![][6.svg]  | ![][7.svg]  | ![][8.svg]  |             |
| 10 |             | ![][11.svg] | ![][12.svg] | ![][13.svg] | ![][14.svg] | ![][15.svg] | ![][16.svg] | ![][17.svg] | ![][18.svg] | ![][19.svg] |
| 20 | ![][20.svg] | ![][21.svg] | ![][22.svg] | ![][23.svg] | ![][24.svg] | ![][25.svg] | ![][26.svg] |             |             | ![][29.svg] |
| 30 | ![][30.svg] | ![][31.svg] | ![][32.svg] | ![][33.svg] | ![][34.svg] | ![][35.svg] | ![][36.svg] | ![][37.svg] | ![][38.svg] | ![][39.svg] |
| 40 | ![][40.svg] | ![][41.svg] | ![][42.svg] | ![][43.svg] | ![][44.svg] |             |             |             |             |             |



You’ll notice there are some gaps in the numbering sequence. I like to think they left some room to add more phenomena later on. Perhaps something like this:

<figure>
<img class="w-500" src="/assets/2023/04/missing-weather.png">
<figcaption>
Eruptions and meteor showers followed by scattered dragons.
</figcaption>
</figure>

- - - - - -

If it’s been warm and sunny, you might hear people say “I’m loving this weather!”. It might be more accurate if they said “I don’t really like…weather”. After all, sunshine is the absence of weather. Weather is everything that gets in between you and the sun. If you fly up through the clouds on a rainy day, you leave most of the weather behind you. If you keep on flying towards the moon, you’ll eventually find yourself in a completely weather-free zone.

It’s always sunny on the moon. Unless it’s night time. If you were preparing a local weather forecast you’d only need two symbols; one for the day and one for the night:

<figure>
<img class="w-400" src="/assets/2023/04/moon-weather.png">
<figcaption>
Tonight’s Earth phase: waxing crescent.
</figcaption>
</figure>

Weather forecasts for neighbouring planets would be slightly more interesting. Take Venus and Mars, for example:

<figure>
<img class="w-500" src="/assets/2023/04/venus-weather.png">
<figcaption>
Forecast for Venus: acid rain, thunderstorms.
</figcaption>
</figure>

<figure>
<img class="w-400" src="/assets/2023/04/mars-weather.png">
<figcaption>
Forecast for Mars: sunny, dust storms.
</figcaption>
</figure>

I tried to organise all of the daytime weather symbols above in a logical way, starting from “null” weather (sunshine) at the top, and deteriorating (or becoming more interesting) as you go down. Here’s what I came up with:

<figure>
<img class="w-500" src="/assets/2023/04/weather-pyramid.png">
<figcaption>

</figcaption>
</figure>

So, what do the unpleasant symbols represent, including the scary one my wife showed me? Inside the svg image files there is a tag with a description of the symbol. My favourite is the double-cloud; it’s called “dreary” which is so much more forlorn than simply “cloudy”.

| Ice         | Sleet/hail  | Freezing rain <br> (icy mix) | Rain and snow <br> (wintry mix) | Dreary <br> (overcast) |
|-------------|-------------|------------------------------|---------------------------------|------------------------|
| ![][24.svg] | ![][25.svg] | ![][26.svg]                  | ![][29.svg]                     | ![][8.svg]             |


Sometimes our weather provider gives us a description of the temperature too, in subjective terms like “pleasant”, or “chilly”. I was intrigued by these terms, so I found the complete table of RealFeel® temperature descriptions[^2], complete with beautiful (and colorblind unsafe) rainbow colour ramp.

<figure>
<img class="w-400" src="/assets/2023/04/realfeel.png">
<figcaption>
Don’t stray too far from the green zone.
</figcaption>
</figure>

For the really low temperatures, the RealFeel guide also lists the time after which you would start to develop frostbite on exposed skin.

<figure>
<img class="w-400" src="/assets/2023/04/frostbite.png">
<figcaption>
If it’s -70°C outside, it’s time to revisit some life choices.
</figcaption>
</figure>

I was intrigued to see what colours were chosen to represent temperatures by weather providers in different countries. I took Australia as my “warm” country, and Iceland as my “cold” country (there are colder places, but nobody would describe Iceland as “hot”). Here are examples of temperature forecast maps from Australia’s WeatherZone[^3] and the Icelandic Met Office[^4].

|---------------------------------------------------|-------------------------------------------------|
| <img src="/assets/2023/04/wz.gfs.aus.sfc.00.png"> | <img src="/assets/2023/04/230329_0600_018.gif"> |


The mean surface temperature on Earth is around 14°C. The ReelFeel guide calls that “cool”, but to the average Icelander that is probably quite toasty. I made a widget to compare the colours used to represent the range from the coldest temperature I could find on the historical Iceland weather maps (-26°C) to the highest temperatures on the Australia weather maps (54°C).



<iframe src="/assets/2023/04/weather-widget.html" width="600px"></iframe>

Here are the full colour ramps:

<figure>
<img class="w-500" src="/assets/2023/04/ramps.png">
<figcaption>
Green does not mean “pleasant” in Iceland, apparently.
</figcaption>
</figure>

The ReelFeel guide describes the range from 17°C to 26°C as “pleasant”. That’s a pretty narrow range in which humans can feel comfortable. Is there anywhere on Earth where the weather is always pleasant? The climate of Düsseldorf, the city which my family currently calls home, is classified as temperate. Summers can be great, but winters are not. Here are the average monthly temperatures from open source data provider MeteoStat[^5]:

<figure>
<img class="w-500" src="/assets/2023/04/dus-climate.png">
<figcaption>
There is pleasantness to be had, but not always.
</figcaption>
</figure>

I then went on a search for cities with the most agreeable (and punishing) climates I could find.

<figure>
<img src="/assets/2023/04/climates-dark.png">
<figcaption>
Apparently summers in Yakutsk are sunny and warm (but short).
</figcaption>
</figure>

Unfortunately I don’t think any city can guarantee year-round pleasantness, but you might get close by moving to a small island close (but not too close) to the equator. Not surprising, really.

#### References

[^1]: [AccuWeather](https://www.accuweather.com/)
[^2]: [AccuWeather RealFeel Guide](https://www.accuweather.com/en/weather-news/accuweather-realfeel/784)
[^3]: [WeatherZone models](https://www.weatherzone.com.au/models/charts/gfs/aus)
[^4]: [Icelandic Met Office forecasts](https://en.vedur.is/weather/forecasts/elements/#type=temp)
[^5]: [Meteostat](https://dev.meteostat.net/)

<!-- Links to svg files -->
[1.svg]: /assets/2023/04/1.svg
[2.svg]: /assets/2023/04/2.svg
[3.svg]: /assets/2023/04/3.svg
[4.svg]: /assets/2023/04/4.svg
[5.svg]: /assets/2023/04/5.svg
[6.svg]: /assets/2023/04/6.svg
[7.svg]: /assets/2023/04/7.svg
[8.svg]: /assets/2023/04/8.svg
[11.svg]: /assets/2023/04/11.svg
[12.svg]: /assets/2023/04/12.svg
[13.svg]: /assets/2023/04/13.svg
[14.svg]: /assets/2023/04/14.svg
[15.svg]: /assets/2023/04/15.svg
[16.svg]: /assets/2023/04/16.svg
[17.svg]: /assets/2023/04/17.svg
[18.svg]: /assets/2023/04/18.svg
[19.svg]: /assets/2023/04/19.svg
[20.svg]: /assets/2023/04/20.svg
[21.svg]: /assets/2023/04/21.svg
[22.svg]: /assets/2023/04/22.svg
[23.svg]: /assets/2023/04/23.svg
[24.svg]: /assets/2023/04/24.svg
[25.svg]: /assets/2023/04/25.svg
[26.svg]: /assets/2023/04/26.svg
[29.svg]: /assets/2023/04/29.svg
[30.svg]: /assets/2023/04/30.svg
[31.svg]: /assets/2023/04/31.svg
[32.svg]: /assets/2023/04/32.svg
[33.svg]: /assets/2023/04/33.svg
[34.svg]: /assets/2023/04/34.svg
[35.svg]: /assets/2023/04/35.svg
[36.svg]: /assets/2023/04/36.svg
[37.svg]: /assets/2023/04/37.svg
[38.svg]: /assets/2023/04/38.svg
[39.svg]: /assets/2023/04/39.svg
[40.svg]: /assets/2023/04/40.svg
[41.svg]: /assets/2023/04/41.svg
[42.svg]: /assets/2023/04/42.svg
[43.svg]: /assets/2023/04/43.svg
[44.svg]: /assets/2023/04/44.svg