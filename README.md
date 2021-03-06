## Chat program with multi-thread
> TCP/IP final exam report

<br/>

## ๐จ๐ปโ๐ป Overview  
    Python ๊ธฐ๋ฐ์ multi-thread ํ์ฉ ์ฑํ ํ๋ก๊ทธ๋จ
[Server](https://github.com/songhwee1/TCP_IP_Chat/blob/main/main/server.py)์ [Client](https://github.com/songhwee1/TCP_IP_Chat/blob/main/main/client.py)๋ก ์ด๋ฃจ์ด์ง <b>๋ค์ค ์ ์ ์ฑํ ํ๋ก๊ทธ๋จ</b> ์๋๋ค.



<br/>


## โ๏ธ Development Purpose
TCP/IP ๊ฐ์์๊ฐ์ ๋ฐฐ์ด multi-thread์ ๊ฐ๋์ ํ์ฉํ์ฌ ํ๋์ ์๋ฒ์ ์ฌ๋ฌ ๋ช์ ํด๋ผ์ด์ธํธ๊ฐ ์ ์ํ์ฌ ์ฑํ์ ์ฃผ๊ณ  ๋ฐ์ ์ ์๋ ํ๋ก๊ทธ๋จ


<br/>


## โ Design and Capabilities
<b>[Server](https://github.com/songhwee1/TCP_IP_Chat/blob/main/main/server.py)</b>์ <b>[Client](https://github.com/songhwee1/TCP_IP_Chat/blob/main/main/client.py)</b>๋ก ๊ตฌ์ฑ๋ฉ๋๋ค.
<b>threading library</b>๋ฅผ ํ์ฉํ์ฌ <b>multi-thread</b>๋ฅผ ๊ตฌํํ์์ต๋๋ค.
<b>tkinter library</b>๋ฅผ ํ์ฉํ์ฌ <b>GUI</b>๋ฅผ ๊ตฌ์ฑํ์์ต๋๋ค.

#### Server.py

   - Class room : ์ฑํ๋ฐฉ ์ ์  ๊ด๋ฆฌ
   
       def addClient : ์ฑํ๋ฐฉ์ ์ฌ์ฉ์๋ฅผ ์ถ๊ฐ
       
       def delClient : ์ฑํ๋ฐฉ์์ ์ฌ์ฉ์๋ฅผ ์ญ์ 
       
       def sendMsgAll : ๋ชจ๋์๊ฒ message ์ ์ก
 
   - Class chatClient : Client์์ ํต์ ์ ๋ด๋น
   
       def recv : while๋ฌธ์ ํตํ์ฌ data์์  ๋ฐ ์์ ๊ฐ์ ๋ฐ๋ฅธ ๊ฒฐ๊ณผ ์คํ ('/์ข๋ฃ': ํด์ฅ ๋ฐ ํด๋ผ์ด์ธํธ ์ญ์ )
       
       def refreshClient: Client๊ฐ ์ ์/ํด์ฅ ํ ๋๋ง๋ค Client๋ชฉ๋ก ์ต์ ํ
       
       def send : ๋ชจ๋  ํด๋ผ์ด์ธํธ์๊ฒ data ์ ์ก
    
   - Class chatServer : server IP address, port ์ค์  ๋ฐ server ์คํ
   
       def open : ์ค์ ๋ IP address์ port ๊ฐ์ผ๋ก TCP socket server ์คํ
       
       def run : open method ์คํ ๋ฐ thread ํ ๋น
       
#### Client.py

   - Class chatClient : client์ server ์ ์ ๋ฐ ํต์ ์ ๋ด๋น
   
       def conn : server ์ ์ ์๋
       
       def ui : GUI ๊ตฌ์ฑ
       
       def userName : ์ต์ด ์ ์์ ์ฌ์ฉํ  ์ด๋ฆ์ ์ ํํ๋ ํ์ ํ์์ GUI
       
       def setUserName : ์ต์ด ์๋ ฅ ๊ฐ์ ์ด๋ฆ์ผ๋ก ์ค์ 
       
       def send : ์๋ ฅํ data๋ฅผ server๋ก ์ ์ก
       
       def recv : server ์์ data ์์  ๋ฐ ํ๋ฉด์ ํ์(์ฑํ ๋ด์ฉ, ์ ์ ์ธ์)
       
       def run : conn, userName, ui method ์คํ ๋ฐ thread ํ ๋น


<br/>


## ๐ก Distinction
- ๋ฒํผ ํด๋ฆญ์ด ์๋ Enter ํค ์๋ ฅ์ ํตํด์๋ data ์ ์ก ๊ฐ๋ฅ
- ์ต์ด ์ ์ ์ ํ์์ฐฝ์์ ๋๋ค์(์ฌ์ฉํ  ์ด๋ฆ) ํ ๋น
- ์๋ก์ด client ์ ์ ์ ์๋ฆผ
- ์ ์์ค์ธ client ๋ชฉ๋ก ํ์
- '/์ข๋ฃ' ์๋ ฅ ์ ์๋ฆผ ๋ฐ ์ข๋ฃ

<br/>


## ๐ฅ Launch Screen
- server ์คํ์

<img src = "img/openServer.JPG">

- client ์คํ์

<img src = "img/clientConnect.JPG">

- ๋๋ค์ ์ค์  ํ๋ฉด

<img src = "img/usernameInput.png">

- ๋ฉ์ธ ํ๋ฉด

<img src = "img/main1.png">

- '/์ข๋ฃ' ์๋ ฅ์

<img src = "img/exit.png">


<br/>


## โ To - Do
๋๋ง์๊ธฐ ๊ฒ์ (ํ์ฌ ์ ๋ถ ์ฃผ์์ฒ๋ฆฌ)
- txt ํ์ผ์ dataset ์ ์
- '/์์'์ ์๋ ฅํ์ฌ ๊ฒ์ ์์
- 1์ธ ํ๋ ์ด๋ ์ ์์ ์ผ๋ก ์งํ๋จ
- ๋ค๋ฅธ client๋ค๊ณผ ์ฐ๋๋์ง ์๋ issue ๋ฐ์. 


<br/>


## ๐ง Tech

BE(Back-End) :
```
Python 3.9.2
```

FE(Front-End) :
```
Python 3.9.2 (tkinter)
```


