Trả lời các câu hỏi để nhận được kho báu

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Tìm Gift Code</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        .question {
            margin: 20px 0;
        }
        .hidden {
            display: none;
        }
        #gift-code {
            font-size: 24px;
            color: green;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Trả lời đúng để nhận Gift Code!</h1>
    <div id="questions">
        <div class="question"><p>Câu 1: Tên của bạn là?</p><input type="text" id="q1"></div>
        <div class="question"><p>Câu 2: Bạn đang yêu ai?</p><input type="text" id="q2"></div>
        <div class="question"><p>Câu 3: Ngày đầu tiên hai bạn gặp nhau?</p><input type="text" id="q3"></div>
        <div class="question">
            <p>Câu 4: Món ăn yêu thích của Vũ?</p>
            <label><input type="radio" name="q4" value="A">A. Thịt</label>
            <label><input type="radio" name="q4" value="B">B. Cá</label>
            <label><input type="radio" name="q4" value="C">C. Gà</label>
            <label><input type="radio" name="q4" value="D">D. Rau</label>
        </div>
        <div class="question"><p>Câu 5: "NCGC!" có nghĩa là gì?</p><input type="text" id="q5"></div>
        <div class="question"><p>Câu 6: Thứ đầu tiên anh ấy xin đụng vào người bạn là gì?</p><input type="text" id="q6"></div>
        <div class="question"><p>Câu 7: Công ty anh ấy đang đầu tư?</p><input type="text" id="q7"></div>
        <div class="question"><p>Câu 8: Biệt hiệu anh ấy đặt cho bạn?</p><input type="text" id="q8"></div>
        <div class="question"><p>Câu 9: Cá gì hay bị body shaming?</p><input type="text" id="q9"></div>
        <div class="question"><p>Câu 10: Cá gì ngược lại với tên bạn?</p><input type="text" id="q10"></div>
        <div class="question"><p>Câu 11: Cá gì rất giàu tinh bột?</p><input type="text" id="q11"></div>
        <div class="question">
            <p>Câu 12: Tại sao hai bạn quay về từ rừng?</p>
            <label><input type="radio" name="q12" value="A">A. Ba gọi về</label>
            <label><input type="radio" name="q12" value="B">B. Anh đau bụng</label>
            <label><input type="radio" name="q12" value="C">C. "Mở màn phim kinh dị nè bé"</label>
        </div>
        <div class="question"><p>Câu 13: Lúc ở Huế, bạn dắt anh ấy đi con đường rất đáng sợ, hai bạn lúc đó đang đi tìm ăn món gì?</p><input type="text" id="q13"></div>
        <div class="question">
            <p>Câu 14: Ở Đà Nẵng, bạn giận vì?</p>
            <label><input type="radio" name="q14" value="A">A. Nhìn cô gái khác</label>
            <label><input type="radio" name="q14" value="B">B. Món bạn ghét</label>
            <label><input type="radio" name="q14" value="C">C. Kéo giò tắm biển</label>
        </div>
        <div class="question">
            <p>Câu 15: Ở Hội An, anh ấy làm gì đặc biệt cho bạn?</p>
            <label><input type="radio" name="q15" value="C">C. Sấy tóc</label>
<label><input type="radio" name="q15" value="B">B. Ôm bạn</label>
<label><input type="radio" name="q15" value="A">A. Dắt bạn đi chụp hình</label>
        </div>
        <div class="question"><p>Câu 16: Bạn ăn bao nhiêu tô bún Bà Lan lúc ở Tam Kỳ?</p><input type="text" id="q16"></div>
        <div class="question">
            <p>Câu 17: Bạn đến Huế bằng?</p>
            <label><input type="radio" name="q17" value="A">A. Tàu hỏa</label>
<label><input type="radio" name="q17" value="B">B. Xe máy</label>
<label><input type="radio" name="q17" value="C">C. Chạy bộ</label>
        </div>
        <div class="question">
            <p>Câu 18: Ở Đà Lạt, hai bạn làm gì đặc biệt?</p>
            <label><input type="radio" name="q18" value="D">D. Chạy bộ cùng nhau và anh thực sự hạnh phúc khi nhìn bé đạp xe lúc hoàng hôn cứ thong dong lẽo đẽo theo anh</label>
<label><input type="radio" name="q18" value="C">C. Ăn lẩu</label>
<label><input type="radio" name="q18" value="B">B. Xem review phim cùng nhau</label>
<label><input type="radio" name="q18" value="A">A. Mở máy điều hòa siêu lạnh</label>
        </div>
        <div class="question"><p>Câu 19: Gõ "Em yêu anh".</p><input type="text" id="q19"></div>
        <button onclick="checkAnswers()">Nộp Bài</button>
    </div>
    <div id="result" class="hidden">
        <p>Chúc mừng! Mã của bạn: <span id="gift-code">62439847</span></p>
        <p>Xin vui lòng đem mã đến ngân hàng và CMT để nhận quà. Anh yêu em! KIMCHI</p>
    </div>
    <script>
        const correctAnswers = {
            q1: "lê thị kim chi", q2: "nguyễn duy vũ", q3: "3/6/2022",
            q4: "B", q5: "nói cái gì chứ", q6: "bụng", q7: "intel",
            q8: "gỏi măng cụt", q9: "cá mập", q10: "cá thu", q11: "cá cơm",
            q12: "C", q13: "bánh ép", q14: "C", q15: "C", q16: "2",
            q17: "A", q18: "D", q19: "em yêu anh"
        };

        function checkAnswers() {
            const userAnswers = {
                q1: document.getElementById("q1").value.trim().toLowerCase(),
                q2: document.getElementById("q2").value.trim().toLowerCase(),
                q3: document.getElementById("q3").value.trim(),
                q4: document.querySelector('input[name="q4"]:checked')?.value,
                q5: document.getElementById("q5").value.trim().toLowerCase(),
                q6: document.getElementById("q6").value.trim().toLowerCase(),
                q7: document.getElementById("q7").value.trim().toLowerCase(),
                q8: document.getElementById("q8").value.trim().toLowerCase(),
                q9: document.getElementById("q9").value.trim().toLowerCase(),
                q10: document.getElementById("q10").value.trim().toLowerCase(),
                q11: document.getElementById("q11").value.trim().toLowerCase(),
                q12: document.querySelector('input[name="q12"]:checked')?.value,
                q13: document.getElementById("q13").value.trim().toLowerCase(),
                q14: document.querySelector('input[name="q14"]:checked')?.value,
                q15: document.querySelector('input[name="q15"]:checked')?.value,
                q16: document.getElementById("q16").value.trim(),
                q17: document.querySelector('input[name="q17"]:checked')?.value,
                q18: document.querySelector('input[name="q18"]:checked')?.value,
                q19: document.getElementById("q19").value.trim().toLowerCase()
            };

            const allCorrect = Object.keys(correctAnswers).every(
                key => userAnswers[key] === correctAnswers[key]
            );

            if (allCorrect) {
                document.getElementById("questions").classList.add("hidden");
                document.getElementById("result").classList.remove("hidden");
            } else {
                alert("Sai rồi, thử lại nhé!");
            }
        }
    </script>
</body>
</html>
