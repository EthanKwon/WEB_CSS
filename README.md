# WEB_CSS

### 1. GRID - display:grid

#### 부모에게 부여하는 속성

display:grid를 부모의 스타일에 주고, 자식을 자동으로 grid 값에 넣어 준다.

- [x] grid-template-columns : 열에 대한 넓이 값을 주어 그리드를 준다. (세로줄)
- [x] grid-template-rows : 행에 대한 넓이 값을 주어 그리드를 준다. (가로줄)
- [x] grid-gap : 각 그리드 사이의 간격을 준다.

ex) grid-template-columns : 10px 30px 로 주어지고 grid-template-rows : 5px 10px로 주어지면,
자식 4개에 각각 10px/5px | 30px/5px | 10px/10px | 30px/10px 의 크기를 준다.

- [x] grid-auto-flow : 나머지 child를 어떤것을 기준으로 자동 정렬할지 정한다. (기본 - row)
- [x] grid-auto-row : 주어진 column에 대해 얼마만큼의 넓이 값으로 자동 정렬할지 정한다.
- [x] grid-auto-column : 주어진 row에 대해 얼마만큼의 넓이 값으로 자동 정렬할지 정한다.

* [x] grid-template-areas : 직접 area를 만들고 각각 child에게 area를 부여하여 grid를 준다. (이때, grid-auto-rows등을 이용하여 기준을 잡아야 한다.)
* [x] grid-area : 자식에게 area를 부여한다. (child에게 속성 부여)

ex)

```
    .father {
            display: grid;
            grid-auto-rows: 100px;
            grid-gap: 5px;
            grid-template-areas:
            "header header header"
            "content content sidebar"
            "content content sidebar"
            "footer footer footer";
        }
        .first {
            grid-area: header;
            background-color: #f6e58d;
        }

        .second {
            grid-area: sidebar;
            background-color: #badc58;
        }

        .third {
            grid-area: footer;
            background-color: #686de0;
        }
        .fourth {
            grid-area: content;
            background-color: #ff7979;
        }
```

- [x] fr Unit : 전체 넓이를 균등하게 분배해 준다.

ex) grid-template-columns : 2fr 3fr 2fr 4fr 이라고 하면, 전체를 11로 쪼개서 각각의 fr만큼 넓이를 분배한다.

- [x] repeat : 주어지지 않은 부분도 분해 할 수 있도록 할 수 있다.
- [x] minmax : object가 가져야할 최소 크기를 정할수 있도록 한다. (최소값을 유지할 수 있도록 한다.)
- [x] max-content : 안에 내용이 가장 많은 공간을 사용하도록 한다. (title 설정시 많이 사용)
- [x] min-content : 안에 내용이 가장 적은 공간을 사용하도록 한다.

- [x] auto-fit : content의 크기를 유동적으로 변경시켜 최대한 채운다.
- [x] auto-fill : ghost gird 를 생성해 최대한으로 채운다.

* [x] justify-content : grid 전체를 움직이며, 가로의 위치를 조정한다.
* [x] align-content : grid 전체를 움직이며, 세로의 위치를 조정한다.
* [x] place-content : justify-content와 align-content을 한번에 조정한다.

- [x] justify-items : 각 grid의 내부를 움직이며, 가로의 위치를 조정한다.
- [x] align-items :각 grid의 내부를 움직이며, 세로의 위치를 조정한다.
- [x] place-items : justify-items와 align-items를 한번에 조정한다.

#### child에게 부여하는 속성

- [x] grid-column-start : 부모의 display가 grid인 경우, child의 속성 값으로 사용할수 있다. 해당 element의 가로 시작 line을 설정한다.
- [x] grid-column-end : 부모의 display가 grid인 경우, child의 속성 값으로 사용할수 있다. 해당 element의 가로 끝 line을 설정한다.

* [x] grid-row-start : 부모의 display가 grid인 경우, child의 속성 값으로 사용할수 있다. 해당 element의 세로 시작 line을 설정한다.
* [x] grid-row-end : 부모의 display가 grid인 경우, child의 속성 값으로 사용할수 있다. 해당 element의 세로 끝 line을 설정한다.

* [x]] line-naming : grid-template에서 []를 이용하여 컨텐츠 사이사이의 line에 이름을 붙여 줄수 있다.
* [x] grid-auto-flow : 앞 요소로 인해 만들어진 빈칸을 다음 요소가 채울수 있도록 설정 가능하게 해 준다.

* [x] span : grid-column, grid-row 에서 사용하며, line 기준을 grid 기준으로 바꾼다.

* [x] grid-area : child에게 속성을 줄 경우, row-start / colomn-start / row-end / column-end 의 순서로 속성을 부여한다. (span의 경우, row/column의 순서이다.)

- [x] justify-self : gird 내부 child에게 속성을 부여하며, 가로의 위치를 조정한다.
- [x] align-self : gird 내부 child에게 속성을 부여하며, 세로의 위치를 조정한다.
- [x] place-self : justify-items와 align-items를 한번에 조정한다.
