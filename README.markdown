JavaScript Image ASCIIfier
============================

The ASCIIfier grabs the image from the page and paints it on a hidden canvas element.
The pixel data can then be retrieved from the canvas via getImageData() and converted into ASCII text. The original image is then replaced with the new ASCII image.
Only every other line in the image is used, since the characters used are twice as tall as they are wide.

Usage
---------

- Set to true to convert image to ASCII
	
	asciify=(true/false)

- Set to high to use all pixels in image, medium to use every other and low to use only one in four pixels.
	
	asciiresolution=(low/medium/high)
	
- Set to 1 to maintain the size of the original image, 2 to double the size, etc.

	asciiscale=(1-5)

- Set to true to render the characters in color.

	asciicolor=(true/false)

- Set to true to render the characters as colored blocks (only if asciicolor=true).

	asciiblock=(true/false)

- Inverts the character lookup table, so bright becomes dark and vice versa.

	asciiinvert=(true/false)

- Use a custom character lookup table, default is " .,:;+i1tfLCG08@".

	asciichars=("...")

Demo
---------

	<html>
	<head>
		<title>Hapztron JSASCII</title>
		<script type="text/javascript" src="../jsascii.js"></script>
	</head>
	<body>
		<img src="img/hapztron.png" 
			asciify="true" 
			asciiresolution="high"
			asciiscale="3" 
			asciicolor="false"
			asciiblock="true"
			asciiinvert="false"
			style="background-color: #FFFFFF;"
		/>
	</body>
	</html>

Issues and compatibility
---------

- Only works in <canvas> capable browsers (no IE)
- Tested and should work in (at least) Firefox 2 + 3 and Opera 9.5+.
- There are a bunch of issues with the rendering in Opera, so try different combinations of asciiresolution and asciiscale.

Reference
---------
Original from http://www.nihilogic.dk/labs/jsascii
