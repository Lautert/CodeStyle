# Usando Java no VSCode

Para configurar seu ambiente Java no VSCode vamos necessitar de alguns _plugins_:

## _Plugins_

- [Java Extension Pack] - Já vai lhe fornecer boa parte da stack
    - [Language Support for Java(TM) by Red Hat]
    - [Debugger for Java]
    - [Java Test Runner]
    - [Maven for Java]
    - [Project Manager for Java]
    - [Visual Studio IntelliCode]
- [Java Code Generators] - Excelente para matar coisos simples como GET/SET
- [Lombok Annotations Support for VS Code] - Para quem usa Lombok
- [EditorConfig for VS Code] - Importante para manter os projetos padrões

## _Aplicando o formatador_

- Abrir as configurações (ctrl+,), Arquivo->Preferências->Configurações
- Abrir o formato JSON do canto superior diretor  
    [![JSON-Config-VSCode](https://raw.githubusercontent.com/Lautert/CodeStyle/master/images/json-config-vscode.png)](https://raw.githubusercontent.com/Lautert/CodeStyle/master/images/json-config-vscode.png)
- La vamos inserir 2 configurações extras
``` Json
    "java.format.settings.url": "https://raw.githubusercontent.com/Lautert/CodeStyle/main/custom-code-style.xml",
    "java.format.settings.profile": "Custom Java Formatter",
```

## _Alternando entre JDKs_

- Aperte f1 para abrir o _Command Palette_
- Digite: "Java: Configure Java Runtime"
- Em "Install A JDK" seleciona a versão desejada
    - Se Você ainda não tem ela instalada em seu computador o link de _Download_ fornece a versão
    - Para verificar as versões que ele encontrou em seu computador acesse a aba "installed JDKs"


## _Extras_

Se você estiver usando Windows e assim como eu prefere o gitbash ao powershell, para configurá-lo basta fazer o seguinte:

- Primeiramente baixe o [Git] e realize a instalação (Pressuponho que você vai instalar no local padrão "C:\Program Files\Git")
- Abrir as configurações (ctrl+,), Arquivo->Preferências->Configurações
- Abrir o formato JSON do canto superior diretor  
    [![JSON-Config-VSCode](https://raw.githubusercontent.com/Lautert/CodeStyle/master/images/json-config-vscode.png)](https://raw.githubusercontent.com/Lautert/CodeStyle/master/images/json-config-vscode.png)
- La vamos inserir 2 configurações extras
``` Json
"terminal.external.windowsExec": "C:\\Program Files\\Git\\bin\\bash.exe",
"terminal.integrated.defaultProfile.windows": "Git Bash",
```

   [Java Extension Pack]: <https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack>
   [Language Support for Java(TM) by Red Hat]: <https://marketplace.visualstudio.com/items?itemName=redhat.java>
   [Debugger for Java]: <https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-debug>
   [Java Test Runner]: <https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test>
   [Maven for Java]: <https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven>
   [Project Manager for Java]: <https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-dependency>
   [Visual Studio IntelliCode]: <https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode>
   [Java Code Generators]: https://marketplace.visualstudio.com/items?itemName=sohibe.java-generate-setters-getters
   [Lombok Annotations Support for VS Code]: <https://marketplace.visualstudio.com/items?itemName=GabrielBB.vscode-lombok>
   [EditorConfig for VS Code]: <https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig>
   [Git]: <https://git-scm.com/downloads>