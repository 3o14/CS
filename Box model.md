# ._.) 박스 모델에 대해서 알아보자!
### CSS가 표시하는 모든 것은 박스로 이루어져있다. 
### 따라서 CSS Box Model를 이해하는 것은 매우 중요
<br>

## 🖥 Box Model?
* 모든 Html 엘리먼트는 Box이다.

* 그리고 모든 Box 3개의 층으로 이루어져있다.

* `margin`, `border`, `padding` 그리고 `content`

<p align="center">
<img src="../../img/BoxModel.png">
</p>
<br><br>

## 🖥 박스 모델의 구성요소
### 1. margin
  * 가장 외곽의 층
  
  * 주변에 위치한 다른 엘리먼트와의 상하좌우 간격을 두기 위해서 쓰인다.
### 2. border
  * 경계선을 그리는 층
  
  * 두께 뿐만 아니라 색상과 모양까지 지정할 수 있다.
### 3. padding
  * 컨텐츠와 경계선 사이의 간격을 지정하기 위해서 쓰인다.

### _🖐🏻 잠깐! 여기서 컨텐츠란? - content_
  * 박스에서 가장 중간에 있는 영역
  * `width`(너비)와 `height`(높이)를 지정해줄 수 있다.
  
  <p align="center">
  <img src="./img/BoxModel2.png">
  </p>
<br><br>

## 🖥 Box-Sizing
### 1. content-box
```css
box-sizing: content-box
```
* `box-sizing` 속성의 기본값

* `width` 속성값이 순수하게 `content` 영역의 너비만을 포함

* `margin`값과 `border`, `padding` 값은 `width`에 포함되지 않는다.

### 2. border-box
```css
box-sizing: border-box
```
* `width` 속성값은 `content` 영역뿐만 아니라 `padding`과 `border`까지 포함시키게 된다.
<br/><br/><br/>

***
## 참고
* [DaleSeo - CSS 박스 모델과 box-sizing 속성](https://www.daleseo.com/css-box-model/)
* [Live passionate - [CSS] CSS 기본 박스 모델(Box Model)](https://mjmjmj98.tistory.com/14)
* [TCP school.com - 박스 모델](http://www.tcpschool.com/css/css_boxmodel_boxmodel)
