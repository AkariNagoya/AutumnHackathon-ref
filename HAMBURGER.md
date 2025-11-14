```bash
ハンバーガーメニューhtml（参考）
<header>
  <button class="hamburger" id="hamburger">
    <span></span>
    <span></span>
    <span></span>
  </button>
  <nav id="nav">
    <ul>
      <li>自由</li>
      <li>自由</li>
      <li>自由</li>
    </ul>
  </nav>

ハンバーガーメニューjs（参考）
const hamburger = document.getElementById('hamburger');
const nav = document.getElementById('nav');

  // クリックしたらisOpenクラスが取り外しされる
hamburger.addEventListener('click', ()=> {
  hamburger.classList.toggle('isOpen');
  nav.classList.toggle('isOpen');
});

ハンバーガーメニューcss（参考）
/* ハンバーガーメニューのcss確認 （レスポンシブのみに使う場合）*/
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header{
  background-color: aquamarine;
  width: 100%;
  height: 100px;
  /* position-fixedでヘッダーを固定します */
  position: fixed;
  /* align-itemsはdisplay:flexを使う必要がある */
  display: flex;
  align-items: center;
}

nav ul{
  /* flexを親要素にしないとgapが効かない！gapは親がつけて子要素に対して効く */
  display: flex; 
  gap: 20px;
}

.title{
  display: inline-block;
}

@media screen and (max-width: 767px) {
  nav ul{
    /* opacity0で見えなくする */
    opacity: 0;
  }

  .nav.isOpen ul{
    /* isOpenのとき1にして見えるようにする */
    opacity: 1;
    background-color: white;
    position: fixed;
    width: 100%;
    height: 50vh;
    left: 0;
    top: 0;
    /* メニューを横並びから縦並びに変えるためのもの */
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .hamburger span{
    display: block;
    width: 30px;
    height: 2px;
    background-color: darkred;
    position: relative;
    z-index: 1000;
  }

.hamburger span:nth-of-type(1){
  top: -7px;
}

.hamburger span:nth-of-type(2){
  top: 0px;
}

.hamburger span:nth-of-type(3){
  top: 7px;
}

.hamburger.isOpen span:nth-of-type(1){
  transform: rotate(40deg) translate(18px, 7.5px);
  transition: 0.3s linear;
}

.hamburger.isOpen span:nth-of-type(2){
  display: none;
  transition: 0.3s linear;
}

.hamburger.isOpen span:nth-of-type(3){
  transform: rotate(-40deg) translate(8px, 7.5px);
  transition: 0.3s linear;
}

}

