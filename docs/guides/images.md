# Images

If you are hosting your web app on a web server (like you should) then there is really not much to consider regarding images, other than for you to minimise file sizes to improve app load times.  Images are often cached so subsequent loads are less of an issue.

If you are streaming HTML from SAS though, images are more of a challenge.  This is where `base64` encoding comes in.  Essentially this technique lets you save an image as a long string, eg:


There are many online services that will convert an image into a Base64 string for you, eg:  [https://base64.guru/converter/encode/image](https://base64.guru/converter/encode/image).

When streaming through _webout, be aware that you are likely to hit the line  length restriction.  To avoid this, set a large value for `lrecl` and ensure that your data is streamed byte by byte.

If you use the `sasjs-cli` tool, this part will be handled for you.