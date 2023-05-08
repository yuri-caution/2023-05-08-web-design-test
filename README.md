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