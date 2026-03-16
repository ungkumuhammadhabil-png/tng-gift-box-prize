<!DOCTYPE html>
<html>
<head>
<title>Friend Location Share</title>
</head>
<body style="font-family: Arial; text-align:center; margin-top:50px;">

<h2>Share Your Location</h2>
<p>This page will ask permission to open your location in Google Maps.</p>

<button onclick="shareLocation()" style="padding:10px 20px; font-size:16px;">
Share My Location
</button>

<p id="status"></p>

<script>
function shareLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(function(position) {

      let lat = position.coords.latitude;
      let lon = position.coords.longitude;

      document.getElementById("status").innerHTML =
      "Location found! Opening map...";

      window.open("https://www.google.com/maps?q=" + lat + "
                ," + lon);

    }, function() {
      document.getElementById("status
