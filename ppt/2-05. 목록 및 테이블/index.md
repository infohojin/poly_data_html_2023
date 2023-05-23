## 목록과 링크 스타일   

CSS에서 목록과 링크의 스타일을 변경하는 방법에 대해 설명

목록 스타일 변경하기:

CSS에서 목록의 스타일을 변경하려면 `list-style-type` 속성을 사용합니다.

일반적으로 사용되는 목록 스타일 유형   

- 순서 없는 목록의 불릿 없애기/바꾸기
1. none: 목록의 불릿을 제거합니다.
2. disc: 원형 불릿을 사용합니다. (기본값)
3. circle: 빈 원형 불릿을 사용합니다.
4. square: 사각형 불릿을 사용합니다.

``` html
<style>
/* 순서 없는 목록의 불릿 없애기 */
ul {
  list-style-type: none;
}
</style>
```

- 순서 목록의 숫자 바꾸기
1. decimal: 숫자로 목록을 표현합니다.
2. lower-alpha: 소문자 알파벳으로 목록을 표현합니다.
3. upper-alpha: 대문자 알파벳으로 목록을 표현합니다.
아래는 CSS를 사용하여 목록 스타일을 변경하는 예시입니다:

- list-style-type속성 도서시리즈 예시
``` html
<style>
    /* 소문자 알파벳 */
    .book1 {
      list-style-type:lower-alpha; 
    }
    /* 대문자 로마 숫자 */
    .book2 {
      list-style-type: upper-roman; 
    }
    .inside {
      list-style-position:inside;
  }
 </style>

 <ol class="book1">
    <li>Do it! 시리즈</li>
    <li>된다 시리즈</li>
    <li>DCM 프로 사진가</li>
    <li>데이터과학 시리즈</li>
  </ol>

  <ol class="book2">
    <li>Do it! 시리즈</li>
    <li>된다 시리즈</li>
    <li>DCM 프로 사진가</li>
    <li>데이터과학 시리즈</li>
  </ol>

    <h3> list-style-position을 지정하지 않음</h3>
    <ul> …… </ul>
    <h3> list-style-position : inside</h3>
    <ul class=inside> …… </ul>
```
- 순서 없는 목록의 불릿을 이미지로 바꾸는 속성
``` html
 <style>
    /* 불릿으로 사용할 이미지 */
    ul {
      list-style-image:url('images/dot.png');  
    }
 </style>

```
- 표 스타일
1. caption-side
    - 캡션은 기본으로 표 위쪽에 표시
    - 이 속성을 이용해 아래쪽에 표시 가능
    `caption-side : top | bottom`
2. border
    - 표의 바깥 테두리와 셀 테두리 모두 지정
    ``` html
    <style>
        .table1 {
        border:1px solid black;
        }
        .table1 td {
        border:1px dotted black;
        }
    </style>
    ```
3. border-callapse
    - 표 테두리와 셀 테두리를 합칠 것인지 설정
    `border-collapse : collapse | seperate`
    ```html
    <style>
        .table1 {
        border:1px solid black;
        border-collapse:collapse;
        }
        .table1 td {
        border:1px dashed black;
        }
    </style>
    ```
4. border-spacing
    - border-collapse:seperate를 사용해 셀들을 분리 했을 경우, 인접한 셀 테두리 사이의 거리 지정
    - 값이 1개 : 수평거리 & 수직거리를 같게
    - 값이 2개 : 첫번째 값을 수평거리, 두번째 값은 수직거리
    ```html
    <style>
        .table1 {
        border:1px solid black;
        border-collapse:separate;
        border-spacing:20px 10px;
        }
        .table1 td {
        border:1px solid black;
        }
    </style>
    ```
5. empty-cell
    - border-collapse : seperate를 사용해 셀들을 분리했을 경우, 내용이 없는 빈 셀들의 표시여부를 지정
    `empty-cells : show | hide`
    ```html
        <style>
            .schedule { border-collapse:separate; }
            td { border:1px solid black; }
            #tb1 td{ empty-cells:show; }
            #tb2 td { empty-cells:hide; }
        </style>

        <table class="schedule" id="tb1"> …… </table>  
        <table class="schedule" id="tb2"> …… </table>  
    ```
6. width, height
    - 너비나 높이를 지정하지 안흥면 셀 안의 내용이 표시될 만큼만 표시됨
    - width값을 지정할 경우, padding속성을 이용해 여백을 넣어주면 보기 좋게 꾸밀 수 있음
    ```html
    <style>
        table {
            border-collapse:collapse;
            width:300px;
        }
        td {
            padding:10px;
        }
    </style>
    ```
7. table-layout 
    - 셀 안의 내용 양에 따라 셀 너비를 변하게 할지, 고정시킬지 결정
    `table-layout : fixed | auto`
    ```html
    <style>
        .table1 {
            border-collapse:collapse;
            width:300px;
            table-layout:fixed;
            word-break:break-all;
            height:auto;
        }
        .table1 td {
            width:150px;
            border:1px solid black;
            padding:5px;
        }
    </style>    

    ```
8. text-align
    - 셀 안에서의 수평 정렬 방법
    `text-align : left | right | center`
    ```html
    <style>
    .table1 td {
        text-align:center;
    }
    </style>

    ```
9. vertical-align
    - 셀 안에서의 수직 정렬 방법
    `vertical-align : top | bottom | middle`
    ```html
    <style>
        .va1 { vertical-align:top; }
        .va2 { vertical-align:bottom; }
        .va3 { vertical-align:middle; }
    </style>

    ```