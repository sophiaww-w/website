<!DOCTYPE html>
<html>
<head>
  <title>Global Fundraiser</title>
  <script src="//unpkg.com/globe.gl"></script>
  <style>
    body { margin: 0; }
    #globeViz { width: 100vw; height: 100vh; }
  </style>
</head>
<body>

<div id="globeViz"></div>

<script>
  const locations = [
    {
      lat: 40.7128,
      lng: -74.0060,
      city: "New York",
      country: "USA",
      org: "Helping Hands",
      link: "usa.html"
    },
    {
      lat: -1.2921,
      lng: 36.8219,
      city: "Nairobi",
      country: "Kenya",
      org: "Water Aid",
      link: "kenya.html"
    }
  ];

  const globe = Globe()
    (document.getElementById('globeViz'))
    .globeImageUrl('//unpkg.com/three-globe/example/img/earth-dark.jpg')
    .pointsData(locations)
    .pointLabel(d => `${d.city}, ${d.country} - ${d.org}`)
    .onPointClick(d => {
      window.location.href = d.link;
    });
</script>

</body>
</html>
