# simple-calculator-program-using-Bootstrap
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bootstrap Calculator</title>

  <!-- Bootstrap CSS -->
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
    rel="stylesheet"
  >
</head>
<body class="bg-light d-flex justify-content-center align-items-center vh-100">

  <div class="card shadow-lg" style="width: 300px;">
    <div class="card-body">

      <h4 class="text-center mb-3">Calculator</h4>

      <!-- Display -->
      <input type="text" id="display" class="form-control mb-3 text-end" disabled>

      <!-- Buttons -->
      <div class="row g-2">
        <div class="col-3"><button class="btn btn-secondary w-100" onclick="clearDisplay()">C</button></div>
        <div class="col-3"><button class="btn btn-secondary w-100" onclick="appendValue('/')">÷</button></div>
        <div class="col-3"><button class="btn btn-secondary w-100" onclick="appendValue('*')">×</button></div>
        <div class="col-3"><button class="btn btn-danger w-100" onclick="deleteLast()">⌫</button></div>

        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('7')">7</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('8')">8</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('9')">9</button></div>
        <div class="col-3"><button class="btn btn-secondary w-100" onclick="appendValue('-')">−</button></div>

        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('4')">4</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('5')">5</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('6')">6</button></div>
        <div class="col-3"><button class="btn btn-secondary w-100" onclick="appendValue('+')">+</button></div>

        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('1')">1</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('2')">2</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('3')">3</button></div>
        <div class="col-3" rowspan="2">
          <button class="btn btn-primary w-100" onclick="calculate()">=</button>
        </div>

        <div class="col-6"><button class="btn btn-light w-100" onclick="appendValue('0')">0</button></div>
        <div class="col-3"><button class="btn btn-light w-100" onclick="appendValue('.')">.</button></div>
      </div>

    </div>
  </div>

  <!-- JavaScript -->
  <script>
    let display = document.getElementById("display");

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = "";
    }

    function deleteLast() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>

</body>
</html>
