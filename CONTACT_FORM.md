### 送信フォームhtml（参考）
```bash
     <div class="form-container">
<!-- フォームを作る時はformタグで囲んでね！連続して複数作る時は1つのフォームタグでまとめて囲んでOK！ -->
        <form id="contactForm">
          <div class="form-group">
            <label for="name">お名前</label>
            <input type="text" id="name" name="name" required>
          </div>
          <div>
            <label for="email">メールアドレス</label>
            <input type="email" id="email" name="email" required>
          </div>
          <div class="form-group">
            <label for="phoneNumber">電話番号</label>
            <input type="tel">
          </div>
          <div class="form-group">
            <label for="message">お問い合わせ内容</label>
            <textarea id="message" name="message" required></textarea>
            <button type="submit" class="submit-btn">送信する</button>
          </div>
        </form>
      </div>
```

### 送信フォームjs（参考）
```bash
// 送信フォームのjs
const form = document.getElementById('contactForm');

  form.addEventListener('submit', (e) => {
   e.preventDefault(); // フォームのデフォルト送信を防ぐ

// フォームの値を取得
  const name = document.getElementById('name').value;
  const email = document.getElementById('email').value;
  const phoneNumber = document.getElementById('phoneNumber').value;
  const message = document.getElementById('message').value;

// コンソールに出力
  console.log('=== フォーム送信内容 ===');
  console.log('お名前:', name);
  console.log('メールアドレス:', email);
  console.log('電話番号:', phoneNumber);
  console.log('お問い合わせ内容:', message);

// フォームをリセット
  form.reset();
  });