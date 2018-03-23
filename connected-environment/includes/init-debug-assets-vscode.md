## <a name="initialize-debug-assets-with-the-vs-code-extension"></a>Inicializovat debug prostředky s příponou VS Code
Nejprve musíme nakonfigurujte naše projektu kódu tak, aby VS Code budou komunikovat s našeho vývojového prostředí v Azure. Rozšíření VS Code pro připojené prostředí poskytuje pomocníka příkaz nastavit konfiguraci ladění. 

Otevřete **příkaz palety** (pomocí **zobrazení | Příkaz palety** nabídky) a používání automatické doplňování a vyberte tento příkaz: `Connected Environment: Create configuration files for connected development`. 

Tento postup Přidá konfiguraci ladění pro připojené prostředí v rámci `.vscode` složky.

![](../media/vsce-command-palette.png)

> [!Note]
> **Důležité**: z důvodu chyby, zavřete a znovu ho otevřete VS Code než budete pokračovat.