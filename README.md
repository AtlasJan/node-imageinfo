# node-imageinfo

This is a small package for node.js to allow the analysis of image data in a Buffer, and return mime-type, and image dimensions for the data.

It is designed to be fast, completely written in javascript and have no dependencies on external packages or libraries.

Currently it supports PNG, JPEG, GIF and (uncompressed) SWF analysis.

If you also have zlib available (`npm install zlib`) then it will support compressed SWF files.

## Usage:

To install imageinfo into your project, use `npm install imageinfo`, then it's simply a matter of calling it with the buffer object containing your image, like this:

	var imageinfo = require('imageinfo'),
		fs = require('fs');

	fs.readFile('testimage', function(err, data) {
		if (err) throw err;

		info = imageinfo(data);
		console.log("Data is type:", info.mimeType);
		console.log("  Size:", data.length, "bytes");
		console.log("  Dimensions:", info.width, "x", info.height);
	});

## License:

Project code is released under the CC0 license:

<a rel="license" href="http://creativecommons.org/publicdomain/zero/1.0/">
<img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
</a>
