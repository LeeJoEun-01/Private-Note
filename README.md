# Private-Note

- swql 창 사용법
- 문자열 안에서 변수 사용하는 법 ${}

```javascript
//매체 버튼 그리기
			let provider = $('#select_ad_provider').val();
			if (provider.isEmpty){

			} else{
				for(var i=0; i<provider.length; i++){
					let adprovider = provider[i];
					$('#select_filter_provider').append(`<li class="filter-list">${adprovider}\n` +
							`  <a data-nm="${adprovider}" href="javascript: void(0);" class="sa-warning ml5">\n` +
							'    <i class="fas fa-times-circle"></i>\n' +
							'  </a>\n' +
							'</li>');
				}
			}



			// swal 확인창
			let adProvider = '';
			document.querySelector('#select_filter_provider').addEventListener('click', ({ target }) => {
				if (target.closest('.sa-warning')) {

					target = target.closest('.sa-warning');
					adProvider = `${ target.parentElement.innerText }`;
					// 네이버, 구글 ,다음, 카카오

					swal({
						title: '정말 삭제하시겠습니까?',
						text: '삭제 버튼을 클릭하면 영구적으로 삭제됩니다.',
						type: 'warning',
						showCancelButton: true,
						confirmButtonColor: '#DD6B55',
						confirmButtonText: '확인',
						cancelButtonText: '취소'
					}).then(confirm => {
						if (confirm.value) {
							// 새로 그리기

							target.parentElement.remove();
							//삭제하기 버튼 클릭했을 때
							$('#page-wrapper > main > div > div:nth-child(2) > div > div > div.panel.panel-default.mb0.bb-niherit > div.panel-wrapper.collapse.in > div > div > div:nth-child(3) > div > div.fs-label-wrap > div').click();
							$(`.panel-wrapper .fs-options div[data-value="${adProvider}"] .fs-checkbox`).click();
							console.log(adProvider);
						}
					})
				}
			});
		});
```
