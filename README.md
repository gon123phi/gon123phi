<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Baccarat AI Gợi Ý</title>
</head>
<body>
  <h2>AI Gợi Ý Baccarat</h2>
  <p>Nhập chuỗi kết quả gần nhất (P = Player, B = Banker):</p>
  <input type="text" id="sequence" placeholder="Ví dụ: PPBPB">
  <button onclick="predict()">Dự đoán</button>
  <p id="result"></p>

  <script>
    function predict() {
      let seq = document.getElementById("sequence").value.toUpperCase();
      if (!seq) {
        document.getElementById("result").innerText = "Hãy nhập chuỗi trước!";
        return;
      }
      // Logic dự đoán rất đơn giản: nếu 2 kết quả cuối giống nhau → đoán lặp lại, nếu khác → đảo
      let n = seq.length;
      let guess = "";
      if (n >= 2) {
        if (seq[n-1] === seq[n-2]) {
          guess = seq[n-1]; // theo cầu bám
        } else {
          guess = (seq[n-1] === "P") ? "B" : "P"; // theo cầu đảo
        }
      } else {
        guess = "P"; // mặc định ban đầu
      }
      document.getElementById("result").innerText = "Gợi ý: " + (guess === "P" ? "Player" : "Banker");
    }
  </script>
</body>
</html>
