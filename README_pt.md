# Configurações do novo Windows terminal :star:

Repositório para as configurações do novo [Windows terminal](https://github.com/microsoft/terminal).

- Configurar o Git Bash no [Windows terminal](https://github.com/microsoft/terminal).
- Temas 
- Adicionando o atalho do windows terminal com o botão direito do mouse.

## Configuração do Git Bash

![](https://github.com/GustavoMMartins/windows-terminal-config/blob/master/images/git_bash.jpg)

Basta por o codigo em Json abaixo :point_down:

```
{
    "guid" : "{00000000-0000-0000-0000-000000012345}",
    "closeOnExit" : true,
    "colorScheme" : "Campbell",
    "commandline" : "\"%PROGRAMFILES%\\git\\bin\\bash.exe\" --login -i -l",
    "cursorColor" : "#FFFFFF",
    "cursorShape" : "bar",
    "fontFace" : "Consolas",  
    "historySize" : 9001,
    "icon" : "%PROGRAMFILES%\\git\\mingw64\\share\\git\\git-for-windows.ico",
    "name" : "Git Bash",
    "snapOnInput" : true
},
```

Algumas dessas configurações são para ficar com o padrão de configuração e de coloração do Git Bash dentro do [Windows terminal](https://github.com/microsoft/terminal).

* Obeservação: Caso queira modificar o seu terminal principal basta colocar o guid do git bash no "defaultProfile" :exclamation:

## Temas utilizados

![](https://github.com/GustavoMMartins/windows-terminal-config/blob/master/images/retro_color.jpg)

O tema utilizado como padrão sempre será o do power shell essas configurações utiliza o tema retro do terminal.

```
"schemes": [
    {
        "name": "Retro",
        "background": "#000000",
        "black": "#00ff00",
        "blue": "#00ff00",
        "brightBlack": "#00ff00",
        "brightBlue": "#00ff00",
        "brightCyan": "#00ff00",
        "brightGreen": "#00ff00",
        "brightPurple": "#00ff00",
        "brightRed": "#00ff00",
        "brightWhite": "#00ff00",
        "brightYellow": "#00ff00",
        "cyan": "#00ff00",
        "foreground": "#00ff00",
        "green": "#00ff00",
        "purple": "#00ff00",
        "red": "#00ff00",
        "white": "#00ff00",
        "yellow": "#00ff00"
    }
],
```

## Adicionando o atalho do windows terminal com o botão direito do mouse.

1. O passo a passo pra adicionar o windows terminal com o botão direito do mouse começa colocando o seguinte codigo abaixo :point_down: dentro do profiles das configs

```
"startingDirectory": "."
```

2. Agora basta criar um arquivo com nome de "wt.reg" edita-lo e adicionar o seguinte trecho de codigo :point_down:

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt]
 @="Open Windows Terminal here"

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command]
 @="C:\\Users\\<User>\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe"
```

Observação: Troque o a variável User pelo nome do seu usuário no windows.


3. Basta salvar a edição e depois mesclar o arquivo.


### :collision: Opcional

1. Pegue o icone do [Windows terminal](https://github.com/microsoft/terminal).

2. Crie uma pasta dentro da sua pasta "AppData/Local" com o nome WTerminal (basta digitar %USERPROFILE%/AppData/Local/ dentro do Win + R) e coloque o icone la dentro.

3. Dentro do editor de registros do windows vá para "HKEY_CLASSES_ROOT\Directory\Background\shell\wt" crie uma nova String com o value name de "Icon" e o value data de "%USERPROFILE%/AppData/Local/WTerminal/terminal.ico" e salve o registro.