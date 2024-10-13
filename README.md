# PowerShellでifort(/ifx)ようにsetvarsする.
```bash
C:\Program Files (x86)\Intel\oneAPI
```
にPathを通しておく. s.ps1をこの中に入れる. 以後powershell上で "s" と打つだけでsetvarsできる.


# 補足1
setvarsはpowershellで実行するとうまくいかないので
cmdに渡して実行する必要がある. 下記はs.ps1の中身である.
hoge
```bash
cmd.exe "/K" '"C:\Program Files (x86)\Intel\oneAPI\setvars.bat" && powershell'
```

# 補足2
PowerShellでは次のように起動時に警告されることがある.
新機能と改善のために最新の PowerShell をインストールしてください!https://aka.ms/PSWindows
このMS公式サイトからPowerShell-7.4.5-win-x64.msiをダウンロードしてインストールすると,
エクスプローラのアドレスバーにpwshを入力するとcmdと入力するように開ける.
これはPowerShell Coreというものである.
