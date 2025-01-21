# XXS
## XXS 유형 3가지  
### 1. 반사형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 URL이나 요청에 포함되어 서버에서 직접 실행된 후, 사용자에게 반환. 서버가 응답을 보낼 때 스크립트가 실행 됩니다.
#### 공격 예시: 공격자 가 취약 사이트를 파악하고 URL 줄여 사용자의 메일로 전송 
##### 1. 취약 사이트 파악
![Reflect-XSS](https://github.com/user-attachments/assets/41e99e4a-d27d-4111-b64c-a0623c08e86e)
##### 2. 취약 사이트의 악성 스크립트가 들어간 주소 단축
![image](https://github.com/user-attachments/assets/fd5f69a4-feac-4a95-a049-faeb726fabf9)
##### 3. 사용자에게 메일 전송 후 클릭 시 악성 스크립트 작동
![Reflect-XSS2](https://github.com/user-attachments/assets/889d8594-b625-4836-ae63-1d35522cde16)

### 2. 저장형 XSS (Reflected XSS):  
#### 특징: 공격자의 악성 스크립트가 서버에 저장되고, 이후 여러 사용자가 이 스크립트를 포함한 콘텐츠를 열 때마다 실행 됩니다.
#### 공격 예시: 사용자가 URL에 악성 스크립트가 포함된 링크를 클릭하여 브라우저에서 공격이 실행됩니다.
