# XXS
### 1. 반사형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 URL이나 요청에 포함되어 서버에서 직접 실행된 후, 사용자에게 반환. 서버가 응답을 보낼 때 스크립트가 실행 됩니다.
##### 1. 취약 사이트 파악
![Reflect-XSS](https://github.com/user-attachments/assets/41e99e4a-d27d-4111-b64c-a0623c08e86e)
##### 2. 취약 사이트의 악성 스크립트가 들어간 주소 단축
![image](https://github.com/user-attachments/assets/fd5f69a4-feac-4a95-a049-faeb726fabf9)
##### 3. 사용자에게 메일 전송 후 클릭 시 악성 스크립트 작동
![Reflect-XSS2](https://github.com/user-attachments/assets/889d8594-b625-4836-ae63-1d35522cde16)

### 2. 저장형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 서버에 저장되고, 이후 여러 사용자가 이 스크립트를 포함한 콘텐츠를 열 때마다 실행 됩니다.
#### 1. 공격자가 악성 스크립트를 서버에 저장 -> 사용자가 게시글 혹은 다른 컨테츠를 진입 시 악성 스크립트 작동 합니다.
![Stored-XSS](https://github.com/user-attachments/assets/1099afc9-0b1b-4035-9a13-46ad5c17b71b)

### 3. DOM XSS : 
#### 특징: 공격자의 악성 스크립트가 클라이언트(브라우저)의 자바스크립트 코드에서 실행 됩니다(서버를 거치지 않고 실행된다).
#### 1. 공격자가 악성 스크립트를 서버에 존재.
#### 2. 보다시피 제목이 문자열로 렌더링된 스크립트에서 이미지로 변화.
#### 3. 해당 출력 파트를 textContent -> innerHTML로 변경되어 DOM형식 XSS 해당 출력이 타임리프를 통했다면 저장형 XSS.
![Dom-XSS](https://github.com/user-attachments/assets/420ba2b8-8209-4031-9543-5ee3dadd74c5)
