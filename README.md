# 웹디자인기능사 시험 연습

## ::after 적용
```
.gnb > li > a {
    display: block;
    height: 100px;
    padding: 0 60px;
    line-height: 100px;
    position: relative;
}

.gnb > li > a:hover {
    color: tomato;
}

.gnb > li > a:hover::after {
    content: '';
    position: absolute;
    bottom: 0;
    right: 0;
    width: 15px;
    height: 15px;
    background-color: tomato;    
    border-radius: 100%;
}

.tab_tit {
    display: flex;
    gap: 4px;
    position: relative;
}

.tab_tit::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background-color: tomato;
}
```

## 콘텐츠 정렬
#### div 보다 ul li 가 더 편한 듯
#### a 태그 배먹지 않도록 주의
```
<div class="tab_cont">
    <div class="notice">
        <a href="#">2021년 2월 무이자 할부 카드 안내 2021년 2월 무이자 할부 카드 안내</a>
        <a href="#">쿠폰 사용안내 2021년 2월 무이자 할부 카드 안내</a>
        <a href="#">쿠폰 다운로드 &사용방법</a>
        <a href="#">모바일 APP 설치하고 10% 할인쿠폰 받자!! 2021년 2월 무이자 할부 카드 안내</a>
    </div>
    <ul class="gallery">
        <li><a href="#"></a><img src="./images/gallery1.jpg" alt="어떤 죽음이 삶에게 말했다 책 표지"></a></li>
        <li><a href="#"></a><img src="./images/gallery2.jpg" alt="부모님의 집 정리 책 표지"></a></li>
        <li><a href="#"></a><img src="./images/gallery3.jpg" alt="양말 신은 발 뒷 모습 사진"></a></li>
    </ul>
</div>
```

## grid로 정렬하기
#### display: grid 도 gap 줄 수 있음
```
.links {
    flex: 1;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
}
```

## modal 팝업창 띄우기
#### 마크업 및 css 먼저
```
<div class="modal">
        <h2>2021년 2월 무이자 할부 카드 안내</h2>
        <p>소담스러운 영락과 가장 귀는 얼마나 피고, 이것이다. 길지 끝에 할지라도 청춘의 이것이다. 사라지지 동력은 몸이 만물은 사막이다. 보내는 꽃이 이상의 사랑의 수 말이다. 청춘 동산에는 하는 끓는다. 평화스러운 같은 피부가 오아이스도 위하여 쓸쓸하랴? 천고에 그들의 이상은 가는 원대하고, 부패를 힘있다. 있는 불어 열락의 것은 튼튼하며, 소리다.이것은 그들은 원대하고, 뼈 이것이다. 이상을 심장의 광야에서 일월과 그들은 이상, 것이다. 불어 기관과 오아이스도 운다.</p>
        <a href="#" class="close">닫기</a>
</div>
```
```
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    height: 500px;
    background-color: #ffffff;
    border: 1px solid #666;
    padding: 50px 40px;
    display: none;
}

.modal.active {
    display: block;
}

.modal h2 {
    font-size: 30px;
    margin-bottom: 50px;
}

.modal p {
    line-height: 2;
    font-size: 16px;
}

.modal a {
    display: block;
    width: 100px;
    height: 50px;
    text-align: center;
    line-height: 50px;
    background-color: #ccc;
    position: absolute;
    top: 420px;
    right: 40px;
}
```
### JS script 작업
#### header에 script 추가 잊지 말 것
```
<head>

    <script src="./JS/jquery-1.12.4.js"></script>
    
</head>
```
```
<script>
        $(function(){
            $('.show_modal').click(function(){
                $('.modal').addClass('active')
            })

            $('.close').click(function(){
                $('.modal.active').removeClass('active')
            })
        })
</script>
```

### 서브 메뉴창 나타내고 없애기
```
<script>
        $(function(){
            $('.gnb').mouseover(function(){
                $('.gnb ul').stop().slideDown()
            })          

            $('.gnb').mouseout(function(){
                $('.gnb ul').stop().slideUp('')
            })
        })
</script>
```

### 메뉴창 하이라이트 유지하기
### hover 지정 위치를 어디로 할 것인지 결정
```
.gnb > li:hover > a {
    color: tomato;
}

.gnb > li:hover > a::after {
    content: '';
    position: absolute;
    top: 30px;
    right: 0;
    width: 15px;
    height: 15px;
    background-color: tomato;    
    border-radius: 100%;
}

.gnb ul li:hover a {
    background-color: tomato;
    color: #ffffff;
}
```
