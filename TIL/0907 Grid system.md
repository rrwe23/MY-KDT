## Grid system

- web design

- 요소들의 디자인과 배치에 도움을 주는 시스템

- 기본 요소
  
  - column : 실제 컨텐츠를 포함하는 부분
  
  - Gutter : 칼럼과 칼럼 사이의 공간
  
  - container : 칼럼들을 담고 있는 공간

- Flexbox로 제작됨

- container, rows, column으로 컨텐츠를 배치하고 정렬

### ✔핵심

> 12개의 Column
> 
> 6개의 grid breakpoints

```html
<div class="container">
 <div class="row">
   <div class="col"></div>
   <div class="col"></div>
   <div class="col"></div>
 </div>
</div>   
```

```html
<div class="row g-0 my-3">
g-0 == gutter 0 == 빈틈없이 꽉 채움
```


