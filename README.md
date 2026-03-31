<html>
<head>
  <title>Kastav Tools</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body {
      font-family: Arial;
      text-align: center;
      background: #f4f4f4;
    }
    h1 {
      background: black;
      color: white;
      padding: 15px;
    }
    .box {
      background: white;
      margin: 10px;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 0 10px #ccc;
    }
    input, button {
      padding: 10px;
      margin: 5px;
      width: 80%;
    }
    button {
      background: black;
      color: white;
      border: none;
      border-radius: 5px;
    }
  </style>
</head>

<body>

<h1>🔥 Kastav Tools</h1>

<!-- Age Calculator -->
<div class="box">
  <h3>Age Calculator</h3>
  <input type="date" id="dob">
  <button onclick="age()">Calculate</button>
  <p id="ageRes"></p>
</div>

<!-- EMI Calculator -->
<div class="box">
  <h3>EMI Calculator</h3>
  <input type="number" id="loan" placeholder="Loan Amount">
  <input type="number" id="rate" placeholder="Interest %">
  <input type="number" id="time" placeholder="Years">
  <button onclick="emi()">Calculate</button>
  <p id="emiRes"></p>
</div>

<!-- Percentage -->
<div class="box">
  <h3>Percentage</h3>
  <input type="number" id="total" placeholder="Total">
  <input type="number" id="obtained" placeholder="Obtained">
  <button onclick="per()">Calculate</button>
  <p id="perRes"></p>
</div>

<!-- Love Calculator -->
<div class="box">
  <h3>Love Calculator ❤️</h3>
  <input type="text" placeholder="Name 1">
  <input type="text" placeholder="Name 2">
  <button onclick="love()">Check</button>
  <p id="loveRes"></p>
</div>

<!-- Simple Interest -->
<div class="box">
  <h3>Simple Interest</h3>
  <input type="number" id="p" placeholder="Principal">
  <input type="number" id="r" placeholder="Rate">
  <input type="number" id="t" placeholder="Time">
  <button onclick="si()">Calculate</button>
  <p id="siRes"></p>
</div>

<script>
// Age
function age(){
  let dob = new Date(document.getElementById("dob").value);
  let today = new Date();

  let y = today.getFullYear() - dob.getFullYear();
  let m = today.getMonth() - dob.getMonth();
  let d = today.getDate() - dob.getDate();

  if(d < 0){ m--; d += 30; }
  if(m < 0){ y--; m += 12; }

  document.getElementById("ageRes").innerText =
    `${y}Y ${m}M ${d}D`;
}

// EMI
function emi(){
  let P = loan.value;
  let r = rate.value/100/12;
  let n = time.value*12;

  let e = (P*r*Math.pow(1+r,n))/(Math.pow(1+r,n)-1);
  emiRes.innerText = "EMI: " + e.toFixed(2);
}

// Percentage
function per(){
  let t = total.value;
  let o = obtained.value;
  perRes.innerText = ((o/t)*100).toFixed(2) + "%";
}

// Love
function love(){
  loveRes.innerText =
    "Love: " + (Math.floor(Math.random()*100)+1) + "%";
}

// SI
function si(){
  siRes.innerText = (p.value*r.value*t.value)/100;
}
</script>

</body>
</html>
