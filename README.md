<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>내 IP 주소 확인</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
      background-color: #f0f0f0;
    }
    .container {
      background: white;
      padding: 30px;
      border-radius: 15px;
      display: inline-block;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    h1 {
      margin-bottom: 20px;
    }
    #ip {
      font-size: 24px;
      color: #333;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>당신의 IP 주소는?</h1>
    <p id="ip">불러오는 중...</p>
  </div>

  <script>
    fetch('https://api.ipify.org?format=json')
      .then(response => response.json())
      .then(data => {
        document.getElementById('ip').textContent = data.ip;
      })
      .catch(error => {
        document.getElementById('ip').textContent = 'IP를 불러오는 데 실패했습니다.';
        console.error('IP 가져오기 오류:', error);
      });
  </script>
</body>
</html>
