### 切り替えタブhtml（参考）
```bash
    <div class="tab-container">
      <div class="tab-buttons">
        <button class="tab-button" data-tab="tab1">日本</button>
        <button class="tab-button" data-tab="tab2">イタリア</button>
        <button class="tab-button" data-tab="tab3">ドイツ</button>
      </div>
      <div class="tab-content active" id="tab1">
        <h2>タブ1</h2>
        <p>これはタブ1の内容です。ここに任意のコンテンツを配置できます。</p>
        <p>テキスト、画像、リストなど、何でも入れられます。</p>
      </div>
      <div class="tab-content" id="tab2">
        <h2>タブ2</h2>
        <p>これはタブ2の内容です。ここに任意のコンテンツを配置できます。</p>
        <p>テキスト、画像、リストなど、何でも入れられます。</p>
      </div>
      <div class="tab-content" id="tab3">
        <h2>タブ3</h2>
        <p>これはタブ3の内容です。ここに任意のコンテンツを配置できます。</p>
        <p>テキスト、画像、リストなど、何でも入れられます。</p>
      </div>
    </div>
```

### 切り替えタブjs（参考）
```bash
  // 切り替えタブのJS
  const tabButton = document.querySelectorAll('.tab-button');
  const tabContent = document.querySelectorAll('.tab-content');

  tabButton.forEach(button => {
    button.addEventListener('click', () => {
      // タブIDを取得
      const targetTab = button.getAttribute('data-tab');

      // 全てのボタンとコンテンツからactiveを削除
      tabButton.forEach(btn => btn.classList.remove('active'));
      tabContent.forEach(content => content.classList.remove('active'));

      // クリックされたボタンと対応するコンテンツにactiveを追加
      button.classList.add('active');
      document.getElementById(targetTab).classList.add('active');
    });
  });
```

### 切り替えタブcss（参考）
```bash
/* 切り替えタブのcss */
.tab-container {
  max-width: 800px;
  margin: 0 auto;
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  }

.tab-buttons {
  display: flex;
  background-color: #f0f0f0;
  border-bottom: 2px solid #ddd;
  }

.tab-button {
  flex: 1;
  padding: 1rem;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1rem;
  transition: all 0.3s ease;
  border-bottom: 3px solid transparent;
  }

.tab-button:hover {
  background-color: #e0e0e0;
  }

.tab-button.active {
  background-color: white;
  border-bottom: 3px solid #007bff;
  color: #007bff;
  font-weight: bold;
  }

/* タブのコンテンツ部分 */
.tab-content {
  display: none;
  padding: 2rem;
  animation: fadeIn 0.3s ease;
  }

.tab-content.active {
  display: block;
  }
