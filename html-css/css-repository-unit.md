# css responsive unit

css에서 사이즈를 결정하는 유닛은 절대적인 값, 상대적인 값으로 크게 둘로 나눌 수 있다.
+ Absolute length units(절대적인 값)
  + cm, mm, in, pc, pt, px...등
  + 절대적인 값을 사용하면 컨테이너의 사이즈가 변경 되어도 컨텐츠가 그대로 고정된 값으로 유지된다.    
    사용자가 브라우저에서 폰트 사이즈를 바꿔도 변경이 안된다.

+ Responsive length units(상대적인 값)
  + em, rem, vw, vh, %...등 
  + em : 부모의 사이즈에 따라서 크기가 결정된다.
  + rem : 루트의 사이즈에 따라서 크기가 결정된다.
  + vw, vh : 브라우저의 높이와 너비를 기준으로 결정된다.
  + % : 부모의 사이즈에 따라서 크기가 결정된다.     
  
  + 부모 사이즈에 따라서 변경되어야 한다면 %, em
  + 브라우저 사이즈에 따라서 변경되어야 한다면 v*, rem
  + 요소의 너비와 높이에 따라서 변경되어야 한다면 %, v*
  + 폰트 사이즈에 따라서 변경되어야 한다면 em, rem
  
## em
em은 부모의 사이즈에 따라서 크기가 결정되기 때문에 parent는 우리가 폰트 사이즈를 지정하지 않는 이상   
브라우저에서 html에 할당되는 크기는 16px이므로 16px * 8(em) = 128px이 된다.   
그리고 child는 부모인 parent 사이즈를 기준으로 하기때문에 128px * 0.5(em) = 64px이 된다.   
parent에 작성된 8em을 800%로, child의 0.5em을 50%로 작성해도 동일하다.   

```html
<div class="parent">
  Parent
  <div class="child">
    Child
  </div>
</div>
```

```css
.parent {
  font-size: 8em; /* 16px * 8 = 128px */
}

.child {
  font-size: 0.5em;  /* 128px * 0.5 = 64px */
}
```

## rem
rem은 루트 사이즈에 따라서 크기가 결정되기 때문에 parent는 16px * 8 = 128px이 되고   
child 또한 parent의 사이즈가 아닌 루트 사이즈에 따라 16px * 0.5 = 8px이 된다.   

```html
<div class="parent">
  Parent
  <div class="child">
    Child
  </div>
</div>
```

```css
.parent {
  font-size: 8em; /* 16px * 8 = 128px */
}

.child {
  font-size: 0.5em;  /* 16px * 0.5 = 8px */
}
```

###### 참조 : 유튜버 '드림코딩 by 엘리'
###### PX to EM conversation made simple : http://pxtoem.com/
