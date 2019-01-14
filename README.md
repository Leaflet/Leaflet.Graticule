leaflet.latlng-graticule
===========================

Create a Canvas as ImageOverlay to draw the Lat/Lon Graticule,
and show the grid tick label at the edges of the map.

Check out the [demo](https://leaflet.github.io/Leaflet.Graticule/example/).


### Usage example

```javascript
    L.latlngGraticule({
        showLabel: true,
        zoomInterval: [
            {start: 2, end: 3, interval: 30},
            {start: 4, end: 4, interval: 10},
            {start: 5, end: 7, interval: 5},
            {start: 8, end: 10, interval: 1}
        ]
    }).addTo(map);
```

Or

```javascript
    L.latlngGraticule({
        showLabel: true,
        zoomInterval: [
          {start: 0, end: 1, interval: 90},
          {start: 2, end: 2, interval: 45},
          {start: 3, end: 3, interval: 10},
          {start: 4, end: 5, interval: 5},
          {start: 6, end: 6, interval: 2},
          {start: 7, end: 7, interval: 1},
          {start: 8, end: 8, interval: (30.0 / 60.0)},
          {start: 9, end: 9, interval: (20.0 / 60.0)},
          {start: 10, end: 10, interval: (10.0 / 60.0)},
          {start: 11, end: 11, interval: (5.0 / 60.0)},
          {start: 12, end: 12, interval: (2.0 / 60.0)},
          {start: 13, end: 13, interval: (1.0 / 60.0)},
          {start: 14, end: 15, interval: (0.5 / 60.0)},
          {start: 16, end: 16, interval: (0.2 / 60.0)},
          {start: 17, end: 18, interval: (0.1 / 60.0)},
        ]
    }).addTo(map);
```


### Options
- **showLabel**: Show the grid tick label at the edges of the map. Default `true`
- **opacity**: Opacity of the Graticule and Label. Default `1`
- **weight**: The width of the graticule lines. Default `0.8`
- **color**: The color of the graticule lines. Default `#aaa`
- **font**: Font Style for the tick label. Default `12px Verdana`
- **fontColor**: Color of the tick label. Default `#aaa`
- **format**: Format of labels. Possible values: `dd` for Decimal Degrees, `dmd` for Degrees Decimal Minutes and `dms` for Degrees Minutes Seconds. Default `dd` 
- **precision**: Decimal Degrees precision if format is `dd`. Default `4`
- **zoomInterval**: Use different intervals in different zoom levels. You can set for both latitude and longitude lines as the example, or set different intervals for latitude and longitude like below:
```javascript
  zoomInterval: {
    latitude: [
      {start: 4, end: 6, interval: 5},
      {start: 7, end: 20, interval: 1}
    ],
    longitude: [
      {start: 4, end: 6, interval: 10},
      {start: 7, end: 20, interval: 2}
    ]
  }
```
- ***Default***:
```javascript
  zoomInterval: [
    {start: 2, end: 2, interval: 40},
    {start: 3, end: 3, interval: 20},
    {start: 4, end: 4, interval: 10},
    {start: 5, end: 7, interval: 5},
    {start: 8, end: 20, interval: 1}
  ]
```

#### Special Options
Some of the projections (like Lambert) is no straight line, set those options to draw a polyline graticule.
- **lngLineCurved**: Interval of polyline. Deafult `0`
- **latLineCurved**: Interval of polyline. Deafult `0`

Check out the [Lambert projection example](https://cloudybay.github.io/leaflet.latlng-graticule/example/lambert.html).
