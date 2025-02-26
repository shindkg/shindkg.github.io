---
layout: post
title:  "[Excel] 같은 품목을 찾아서 해당 행의 셀 값 찾기(value, index, match)"
date:   2025-02-14 15:00:00 +0900
categories: [기타, 엑셀]
tags: [excel, index function, match function]
---

지인의 부탁으로 엑셀에서 계산을 해야할 일이 생겼다. 평소 엑셀 쓸 일이 없어서 잘 모르겠지만.. 일단 해본다.  

설명을 들어보니 엑셀 시트A에서 시트B에 있는 품목 중 같은 품목을 찾아서 해당 행에 있는 수량을 찾으면 된다. 그래서 찾아봤다. 


## 💡 1. 문자열을 숫자로 변환

시트A와 시트B에서 숫자로 되어있는 품목 코드가 있다. 그런데 알고보니 숫자가 아니라 문자였다. 수량을 찾는 것이니까 나중에 계산할 수 있도록 문자열을 숫자로 변환하는 VALUE 함수를 사용했다.

`=VALUE(text)`
- text: 텍스트를 숫자로 변환할 수 있다.


## 💡 2. 시트A와 시트B 비교하기

이제 INDEX와 MATCH 함수를 사용하여 시트A와 시트B를 비교하여 같은 품목코드를 찾는다. 

`=INDEX(array, row_num, [column_num])`
- array: 값을 검색할 범위
- row_num: 반환할 값의 행 번호
- column_num: (생략 가능) 반환할 값의 열 번호

`=MATCH(lookup_value, lookup_array, [match_type])`
- lookup_value: 찾고 싶은 값
- lookup_array: 검색할 범위
- match_type: (생략 가능) 일치하는 값을 찾으려면 0, 가까운 값을 찾으려면 1이나 -1 사용

## 💡 3. 같은 품목 코드 찾기


위의 함수를 사용하여 시트A의 품목 코드와 숫자로 바꾼 시트B의 품목 코드인 A1:A5 범위랑 일치하는 값을 찾기 위해 행 번호를 반환하는 MATCH 함수를 사용하고, INDEX 함수로 시트B의 수량 범위인 B1:B5에서 값을 찾아 해당 행 번호와 일치하는 값을 반환한다.

`=INDEX(시트B!B1:B5, MATCH(VALUE("품목 코드"), 시트B!A1:A5, 0))`


