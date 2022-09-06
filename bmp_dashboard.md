# bmp dashboard 개발하기
## [목차]
[1. 개발 요구서](#개발-요구서)  
[2. ZingChart 활용](#ZingChart-활용)  
[3. Ajax 사용하여 데이터 받기](#Ajax-사용하여-데이터-받기)  
[4. dimension과 metrics, size, sort 설정 (setSendData)](#dimension과-metrics,-size,-sort-설정-(setSendData))  
[5. localStorage 구현하기](#localStorage-구현하기)   
[6. selectBox change 잡기](#selectBox-change-잡기)   
[7. Data Attribute](#Data-Attribute)  
[8. swal alert 창](#swal-alert-창)  
[9. 고차함수(filter사용)](#고차함수(filter사용))  
[10. 참고](#참고)

## 개발 요구서
- (디자인된 사이트 사진 첨부)
### 통합 대시보드

### 대시보드 (광고주별)

## 개발 정리 

### ZingChart 활용
- zingchart token 사용
	- 
- tooltip 넣기
### Ajax 사용하여 데이터 받기
### dimension과 metrics, size, sort 설정 (setSendData)
### localStorage 구현하기
### selectBox change 잡기
### Data Attribute
### swal alert 창 
### 고차함수(filter사용)
- reduce, map 도 사용해보자
- 맨 처음에 고차함수 사용안해서 엄청난 양의 반복문과 조건문은 만들었다....ㅎ
- 그러나 코드의 길이가 늘어나서 불편한것은 맞지만 함수를 사용하는 것보다 나중에 다른 개발자들이 보았을 때 직관적으로 이해할 수 있어 유지보수에 도움이 된다.
- 실제로 map이나 reduce의 코드 길이가 짧다고 데이터를 처리하는 속도가 조건문 보다 항상 빠른 것은 아니다 어쩌면 조건문과 반복문을 사용하는 것이 더 빠를수도 있다.
### 참고
- option에 넣어주는 `value 값`들은 생각보다 신중히 넣어야 한다.
- 필요한 데이터가 value에 없다면 `data attribute`를 사용해서 내가 원하는 데이터를 넣어주자
- 아직 이게 무엇인지 모르지만 공부해보쟈

```javascript
<!-- Client seq로 해당 tag를 보여줄지 말지를 결정 -->
<div class="col-md-2 tl w120px" th:if="${session[T(kr.co.bizspring.gp.report.common.ReportProperty).RK_SESSION_CLIENT_SEQ]} > 1">
<!-- 해당 페이지 마다 정보를 가지고와서 알맞는 데이터를 변수에 넣어서 태그를 생성한다. -->
<option th:each="profile:${profileList}" th:value="${profile.pfno}"
				th:text="${profile.profileNm}" selected="selected"></option>
```
- [배열의 깊은 복사와 얕은 복사](https://ecofreenavigator.tistory.com/22)
- [zingChart 참고](https://infofactory0813.tistory.com/14)
- [ZingChart 공식 Docs](https://www.zingchart.com/docs/chart-types/wordcloud)
- [ZingChart 공식 Docs: token에 대하여](https://www.zingchart.com/docs/tutorials/elements/tokens)
=> wordcloud에서 token을 적용해보려고 했지만 실제로 적용되는 토큰이 없어서 다른 방법으로 해결했지만, 평소 다른 데이터 차트는 토큰을 자주 사용한다.
