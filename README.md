<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>Unicorns Info</title>
</head>
<body>

<h1>About Unicorns</h1>
<pre id="unicornText">Loading unicorn info...</pre>

<script>
  // Replace this URL with your actual raw URL to the .txt file on GitHub
  const txtUrl = 'https://raw.githubusercontent.com/yourusername/your-repo/main/unicorns.txt';

  fetch(txtUrl)
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      return response.text();
    })
    .then(data => {
      document.getElementById('unicornText').textContent = data;
    })
    .catch(error => {
      document.getElementById('unicornText').textContent = 'Error loading file.';
      console.error('Fetch error:', error);
    });
</script>

</body>
</html>
