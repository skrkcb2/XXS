# XXS
### 1. 반사형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 URL이나 요청에 포함되어 서버에서 직접 실행된 후, 사용자에게 반환. 서버가 응답을 보낼 때 스크립트가 실행 됩니다.
#### 1. 취약 사이트 파악
![s_REXSS](https://github.com/user-attachments/assets/aa39c1c9-ce41-41b9-9b8b-c9229e84b86c)
#### 2. 취약 사이트의 악성 스크립트가 들어간 주소 단축
![image](https://github.com/user-attachments/assets/fd5f69a4-feac-4a95-a049-faeb726fabf9)
#### 3. 사용자에게 메일 전송 후 클릭 시 악성 스크립트 작동
![s2_REXSS](https://github.com/user-attachments/assets/75fb7db3-9ce3-4f99-9f84-6dce148ad1b9)


### 2. 저장형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 서버에 저장되고, 이후 여러 사용자가 이 스크립트를 포함한 콘텐츠를 열 때마다 실행 됩니다.
#### 1. 공격자가 악성 스크립트를 서버에 저장 -> 사용자가 게시글 혹은 다른 컨텐츠를 진입 시 악성 스크립트 작동 합니다.
![Stored-XSS](https://github.com/user-attachments/assets/1099afc9-0b1b-4035-9a13-46ad5c17b71b)

### 3. DOM XSS : 
#### 특징: 공격자의 악성 스크립트가 클라이언트(브라우저)의 자바스크립트 코드에서 실행 됩니다(서버를 거치지 않고 실행된다).
#### 1. 공격자가 악성 스크립트를 서버에 존재.
#### 2. 보다시피 제목이 문자열로 렌더링된 스크립트에서 이미지로 변화.
#### 3. 해당 출력 파트를 textContent -> innerHTML로 변경되어 DOM형식 XSS 해당 출력이 타임리프를 통했다면 저장형 XSS.
![Dom-XSS](https://github.com/user-attachments/assets/420ba2b8-8209-4031-9543-5ee3dadd74c5)

### 3. XSS 보안 대책? :
#### 3.1 템플릿 엔진 및 백엔드
#### ThymeLeaf: 기본 문법은 th:text 이지만 th:utext(HTML을 그대로 렌더링이 필요할 시 사용)를 사용 금지 혹여 특수 사항 으로 사용 시 백엔드 참고 
![타임리프](https://github.com/user-attachments/assets/696a653f-974b-4e86-b2e7-4444db0e95b9)  
#### JSTL: 타임 리프와 동일 하지만 리스트 데이터 출력의 케이스에서 타임리프와 작은 차이점을 보여준다 아래 이미지는 JSTL과 ThymeLeaf 리스트 출력문 인데 해당의 경우 변수 지정 후 JSTL출력이 아닌 다른 태그에 EL표현으로 쓸수 있지만 ThymeLeaf는 타임리프 출력에 들어가는 순간 JSTL처럼 사용 할수 없다. 반복문에 주의!
![JSTL반복](https://github.com/user-attachments/assets/cb991d2b-7230-48dc-b413-e97d3cb10786) ![타임리프2](https://github.com/user-attachments/assets/1972d57b-cfc6-44f2-8840-8e4a0bc2b483)  
#### React: 리액트의 경우에는 자체적으로 XSS 공격을 방어하는 기능을 제공하며 특수 케이스로 dangerouslySetInnerHTML 사용 시 DOMPurify 라이브러리를 사용하여 sanitize하는 식으로 사용하면 된다  
![React](https://github.com/user-attachments/assets/995d80a0-f1da-46b6-9982-730d1bb9f61a)  
#### 백엔드: 백엔드에서의 조치는 쿠키 설정시 HTTPONLY를 적용하여 스크립트를 통한 쿠키 접근 방지, Jsoup과 같은 라이브러리 를 사용하여 필터링
#### 3.2 자바 스크립트  
#### 자바 스크립트이 경우에는 InnerHTML 대신 textContent를 사용하여 스크립트 방지  
![innerHTML](https://github.com/user-attachments/assets/29faad00-585b-4a1d-be5d-e7f8bb9b79fb)
#### 추가로 정규식 으로의 필터링


