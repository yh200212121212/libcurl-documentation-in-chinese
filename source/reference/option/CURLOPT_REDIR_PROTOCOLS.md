## 声明

```
CURLcode curl_easy_setopt(CURL *handle, CURLOPT_REDIR_PROTOCOLS, long bitmask);
```

## 概要

设置允许重定向的协议。

## 详情

传入一个`long`，该参数持有`CURLPROTO_*`定义的位掩码。如果使用了该选项，在`CURLOPT_FOLLOWLOCATION`启用的情况下，这个位掩码限制了libcurl在传输时可以跟随重定向的协议。这允许你限制特定的传输只能在使用指定协议子集时进行重定向。默认情况下libcurl允许所有的协议，除了FILE和SCP。

下面是可用的协议定义：
```
CURLPROTO_DICT
CURLPROTO_FILE
CURLPROTO_FTP
CURLPROTO_FTPS
CURLPROTO_GOPHER
CURLPROTO_HTTP
CURLPROTO_HTTPS
CURLPROTO_IMAP
CURLPROTO_IMAPS
CURLPROTO_LDAP
CURLPROTO_LDAPS
CURLPROTO_POP3
CURLPROTO_POP3S
CURLPROTO_RTMP
CURLPROTO_RTMPE
CURLPROTO_RTMPS
CURLPROTO_RTMPT
CURLPROTO_RTMPTE
CURLPROTO_RTMPTS
CURLPROTO_RTSP
CURLPROTO_SCP
CURLPROTO_SFTP
CURLPROTO_SMB
CURLPROTO_SMTP
CURLPROTO_SMTPS
CURLPROTO_TELNET
CURLPROTO_TFTP
```

## 默认值

所有协议，除了FILE，SCP和SMB。

## 适用协议

所有协议。

## 可用性

在7.19.4加入，在这之前会跟随所有协议的重定向。

## 返回值

如果支持该选项，返回`CURLE_OK`；否则返回`CURLE_UNKNOWN_OPTION`。