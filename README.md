# PowerShell 上で ifort(/ifx) を実行する.
WindowsにおいてIntel コンパイラ ifort (または ifx) コマンドを実行する前に cmd で環境変数を設定するsetvars.batを実行しなければならない. setvarsはpowershellに対応していなく, 
powershellで実行してもifortが使えるようにならない.
本文書ではPowerShell上でsetvarsを正しく実行する方法を述べる.

## 手順
```bash
C:\Program Files (x86)\Intel\oneAPI
```
にPathを通しておく. 添付のs.ps1をこの中に入れる. 以後powershell上で "s" と打つだけでsetvarsが実行でき, 
ifort (ifx) が使えるようになる.


## 補足 s.ps1
setvarsはpowershellで実行するとうまくいかないので
cmdに渡して実行する必要がある. 下記はs.ps1の中身である.
hoge
```bash
cmd.exe "/K" '"C:\Program Files (x86)\Intel\oneAPI\setvars.bat" && powershell'
```

## 補足 pwsh
エクスプローラのアドレスバーでpowershellと打つとエクスプローラで開いていたフォルダを
カレントディレクトリとしてpowershellを起動することができる.
powershellは単語が長いのでタイプするのが七面倒である.
省略形のpwshを使うには最新のPowerShell (PowerShell Core) をインストールする必要がある.
WindowsPowerShellでは次のように起動時に警告されることがある.
"新機能と改善のために最新の PowerShell をインストールしてください!https://aka.ms/PSWindows"
このMS公式サイトからPowerShell-7.4.5-win-x64.msiをダウンロードしてインストールする.
今後, エクスプローラのアドレスバーにpwshを入力するととエクスプローラで開いていたフォルダを
カレントディレクトリとしてpowershellが起動する
