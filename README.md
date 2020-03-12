# WEB_CSS

### 1. GRID - display:grid 

display:grid를 부모의 스타일에 주고, 자식을 자동으로 grid 값에 넣어 준다.

- [x] grid-template-columns : 열에 대한 넓이 값을 주어 그리드를 준다. (세로줄)
- [x] grid-template-rows : 행에 대한 넓이 값을 주어 그리드를 준다. (가로줄)
- [x] grid-gap : 각 그리드 사이의 간격을 준다. 


ex) grid-template-columns : 10px 30px 로 주어지고 grid-template-rows : 5px 10px로 주어지면,
    자식 4개에 각각 10px/5px | 30px/5px | 10px/10px | 30px/10px 의 크기를 준다.


- [x] grid-auto-flow : 나머지 child를 어떤것을 기준으로 자동 정렬할지 정한다. (기본 - row)
- [x] grid-auto-row : 주어진 column에 대해 얼마만큼의 넓이 값으로 자동 정렬할지 정한다.
- [x] grid-auto-column : 주어진 row에 대해 얼마만큼의 넓이 값으로 자동 정렬할지 정한다.


- [x] grid-template-areas : 직접 area를 만들고 child에게 area를 부여하여 grid를 준다. (이때, grid-auto-rows등을 이용하여 기준을 잡아야 한다.)
- [x] grid-area : 자식에게 area를 부여한다. (child에게 속성 부여)

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