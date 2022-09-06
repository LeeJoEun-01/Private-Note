#Elastic Search로 데이터 확인하는 방법 (IntelliJ 사용)

1. 먼저 코드에 우리가 보고싶은 데이터를 `$(document).ready(function () {` 바로 밑에 세팅한다.
```javascript
				sendAjax(apiUrl + 1000000,
						{
							client_seq: 400004,
							pfno: 53725,
							psDate: '2022-08-30',
							peDate: '2022-09-05',
							ad_provider: '구글,네이버,모비온',
							dimension: 'keyword'
						},
						data => {
							console.log(data);
						});
				return false;
```
2. 코드를 작성한 이후에 Rerun을 하면 run 창에 밑의 사진과 같은 elastic 쿼리문이 떨어지게 된다.
![image](https://user-images.githubusercontent.com/78733700/188757140-47d7863a-4ba7-4774-a3c9-afd8a61db50b.png)
3. 엘라스틱 키바나를 웹에서 켜고 (http://118.67.130.141:5601) -> 메뉴 아이콘을 눌러 Management -> Dev Tools에 들어간다.
 ![image](https://user-images.githubusercontent.com/78733700/188757390-45c55ef3-f585-4cb0-9c69-c6c4330baf88.png)
4. 엘라스틱 console에 인텔리제이에서 가져온 쿼리문을 넣어주고 재생 버튼을 클릭하면
![image](https://user-images.githubusercontent.com/78733700/188757452-2fd9def9-9842-4689-a352-8130208eae23.png)
5. 오른쪽 화면에 데이터가 나온다
![image](https://user-images.githubusercontent.com/78733700/188757696-dfc60e1c-b4e1-4860-a614-cab88f12f430.png)
