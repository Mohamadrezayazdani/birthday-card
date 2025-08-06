<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>کارت تولد</title>
<style>
  body {
    font-family: Tahoma, sans-serif;
    background: #ffe6f0;
    color: #b30059;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    text-align: center;
  }
  .timer {
    display: flex;
    flex-direction: column;
    gap: 12px;
    font-size: 2rem;
    font-weight: bold;
  }
  .time-part {
    background: #fff0f5;
    padding: 20px 40px;
    border-radius: 12px;
    box-shadow: 0 0 8px rgba(179, 0, 89, 0.3);
  }
  #message {
    margin-top: 40px;
    font-size: 1.8rem;
  }
</style>
</head>
<body>

  <div class="timer">
    <div id="days" class="time-part">-- روز</div>
    <div id="hours" class="time-part">-- ساعت</div>
    <div id="minutes" class="time-part">-- دقیقه</div>
    <div id="seconds" class="time-part">-- ثانیه</div>
  </div>

  <div id="message">تولدت مبارک عمر داداش</div>

<script>
  function updateCountdown() {
    const now = new Date();
    const target = new Date(now.getFullYear(), 9, 11, 0, 0, 0); // 11 دی (ماه 9 یعنی دی)
    if (now > target) target.setFullYear(target.getFullYear() + 1);

    const diff = target - now;

    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    const minutes = Math.floor((diff / (1000 * 60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);

    document.getElementById('days').textContent = days + ' روز';
    document.getElementById('hours').textContent = hours + ' ساعت';
    document.getElementById('minutes').textContent = minutes + ' دقیقه';
    document.getElementById('seconds').textContent = seconds + ' ثانیه';
  }

  setInterval(updateCountdown, 1000);
  updateCountdown();
</script>

</body>
</html>
