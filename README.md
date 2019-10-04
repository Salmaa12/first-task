<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="styles.css">
  <title>Color Converter</title>
<meta charset="utf-8">
<title>RGB to HEX Converter</title>
<link href="https://fonts.googleapis.com/css?family=Inconsolata" rel="stylesheet">


<script>
function changeRange() {
    // Get R,G,B values & Convert string into integer.
    var r = parseInt(document.getElementById("r").value);
    var g = parseInt(document.getElementById("g").value);
    var b = parseInt(document.getElementById("b").value);
    // Generate color. Example: #20b9ff
    var color = "#" + hex(r) + hex(g) + hex(b);
    // Change background color and text.
    document.body.style.backgroundColor = color;
    document.getElementById("hex-label").innerText = color;
    document.getElementById("r-label").innerText = r;
    document.getElementById("g-label").innerText = g;
    document.getElementById("b-label").innerText = b;
    if (r < 100 && g < 100 && b < 100) {
        document.getElementById("container").style.color = "white";
    } else {
        document.getElementById("container").style.color = "black";
    }
}
function hex(v) {
    // Get hexadecimal numbers.
    var hex = v.toString(16);
    if (v < 16) {
        hex = "0" + hex;
    }
    return hex;
}
</script>
</head>
<body>
  <h1>Your Favourite Color Converter</h1>
    <div id="container">
        <table>
            <tr>
                <th>Red</th>
                <th>Green</th>
                <th>Blue</th>
            </tr>
            <tr>
                <td><input type="range" min="0" max="255" value="255" id="r" onchange="changeRange()"></td>
                <td><input type="range" min="0" max="255" value="255" id="g" onchange="changeRange()"></td>
                <td><input type="range" min="0" max="255" value="255" id="b" onchange="changeRange()"></td>
            </tr>
            <tr>
                <td id="r-label">255</td>
                <td id="g-label">255</td>
                <td id="b-label">255</td>
            </tr>
        </table>
        <h1 id="hex-label">#ffffff</h1>
    </div>
</body>
</html>
