### Paramiko ile SSH protokolü üzerinde işlemler

+ SSH login süreci

```python
import paramiko
ssh = paramiko.SSHClient()
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
ssh.connect('localhost', username='user', password='pass')
ssh.close()

```

+ Login işleminden sonra komut çalıştırma


```python
stdin,stdout,stderr = ssh.exec_command("pwd")
for i in stdout:
    print i.strip()
```

+ SFTP üzerinden dizin listeleme

```python
sftp = ssh.open_sftp()
print sftp.listdir()

```

+ SFTP üzerinden dizin değiştirme

```python
sftp.chdir("/tmp/")

```

+ SFTP üzerinden dosya yükleme

```python

```

+ SFTP üzerinden dosya indirme

```python


```
