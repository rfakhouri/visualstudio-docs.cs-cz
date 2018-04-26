---
title: Příručka správce Help Viewer
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
ms.assetid: 4340c69f-b96b-4932-bb82-38b16a5ab149
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 19fde51de5e63a0cde9adebd28ad29fc295c6e9e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="help-viewer-administrator-guide"></a>Příručka správce Help Viewer

Help Viewer umožňuje spravovat místní instalace nápovědy pro sítě v prostředích s nebo bez připojení k Internetu. Místní obsah nápovědy je konfigurováno na základě na počítač. Ve výchozím nastavení uživatelé musí mít práva správce k jejich místní Nápověda instalace aktualizace.

Pokud vaše síťové prostředí umožňuje klientům přístup k Internetu, můžete použít **správce obsahu nápovědy** spustitelný soubor pro nasazení obsahu místní nápovědu z Internetu. Další informace o *HlpCtntMgr.exe* řádku syntaxe příkazu najdete v tématu [argumenty příkazového řádku pro správce obsahu nápovědy](../ide/command-line-arguments-for-the-help-content-manager.md).

Informace o vytváření obsahu, vytvoří koncový bod služby intranetu a podobné typy aktivit, najdete v článku [pomoci SDK prohlížeč](../extensibility/internals/microsoft-help-viewer-sdk.md).

Pokud nemáte přístup k Internetu v síťovém prostředí, můžete nasadit Help Viewer místního obsahu nápovědy z intranetu nebo sdílené síťové složce. Nápověda k sadě Visual Studio IDE možnosti lze zakázat i pomocí [klíč registru přepsání](../ide/help-content-manager-overrides.md) pro funkce, jako:

- online a offline nápovědy

- Instalace obsahu při prvním spuštění rozhraní IDE

- určení obsahu služby intranetu

- Správa obsahu

## <a name="deploy-local-help-content-from-the-internet"></a>Nasazení místního obsahu nápovědy z Internetu

Můžete použít **správce obsahu nápovědy** (*HlpCtntMgr.exe*) k nasazení místního obsahu nápovědy z Internetu do klientských počítačů. Použijte následující syntaxi:

```
\\%ProgramFiles(x86)%\Microsoft Help Viewer\v2.3\HlpCtntmgr.exe /operation \<*name*> /catalogname \<*catalog name*> /locale \<*locale*>
```

Další informace o *HlpCtntMgr.exe* řádku syntaxe příkazu najdete v tématu [argumenty příkazového řádku pro správce obsahu nápovědy](../ide/command-line-arguments-for-the-help-content-manager.md).

Požadavky:

-   Klientské počítače musí mít přístup k Internetu.

-   Uživatelé musí mít oprávnění správce k aktualizaci, přidat nebo odebrat místní obsah nápovědy, co byla nainstalována.


Upozornění:

-   Zdroj výchozího nápovědy bude stále online.

### <a name="example"></a>Příklad

Následující příklad nainstaluje anglickou obsah pro sadu Visual Studio ke klientskému počítači.

#### <a name="to-install-english-content-from-the-internet"></a>Chcete-li nainstalovat anglickou obsah z Internetu

1.  Zvolte **spustit** a potom zvolte **spustit**.

2.  Zadejte následující příkaz:

     `C:\Program Files (x86)\Microsoft Help Viewer\v2.3\hlpctntmgr.exe /operation install /catalogname VisualStudio15 /locale en-us`

3.  Stiskněte klávesu **zadejte**.

## <a name="deploy-pre-installed-local-help-content-on-client-computers"></a>Nasazení předem nainstalovaná místní obsah nápovědy na klientských počítačích

Můžete nainstalovat sadu obsahu z online k jednomu počítači a poté zkopírujte tuto nainstalovanou sadu obsahu do jiných počítačů.

Požadavky:

-   Počítač, na kterém instalujete sadu obsahu, který se musí mít přístup k Internetu.

-   Uživatelé musí mít oprávnění správce k aktualizaci, přidat nebo odebrat místní obsah nápovědy, co byla nainstalována.

    > [!TIP]
    > Pokud uživatelé nemají oprávnění správce, doporučujeme zakázat **spravovat obsah** kartě v okně nápovědy. Další informace najdete v tématu [přepsání správce obsahu nápovědy](../ide/help-content-manager-overrides.md).

Upozornění:

-   Zdroj výchozího nápovědy bude stále online.

### <a name="create-the-content-set"></a>Vytvořit sadu obsahu

Před vytvořením základní sady obsahu, musíte nejprve odinstalovat všechny místní obsah sady Visual Studio na cílovém počítači.

#### <a name="to-uninstall-local-help"></a>Chcete-li odinstalovat místní Nápověda

1.  V okně nápovědy, vyberte **spravovat obsah** kartě.

2.  Přejděte do dokumentu sady Visual Studio.

3.  Zvolte **odebrat** vedle jednotlivých podřízených položek.

4.  Zvolte **aktualizace** odinstalovat.

5.  Přejděte do *%ProgramData%\Microsoft\HelpLibrary2\Catalogs\VisualStudio15* a ověřte, že složka obsahuje pouze soubor *catalogType.xml*.

 Odebraný všechny dříve nainstalované místní Visual Studio obsahu nápovědy budete chtít stáhnout základní sady obsahu.

#### <a name="to-download-the-content"></a>Ke stažení obsahu

1.  V okně nápovědy, vyberte **spravovat obsah** kartě.

2.  V části **doporučená dokumentaci** nebo **dostupnou dokumentaci**, přejděte do dokumentace sad, které chcete stáhnout a potom zvolte **přidat**.

3.  Zvolte **aktualizace**.


Dále musíte balíčku obsahu, aby se dala nasadit do klientských počítačů.

#### <a name="to-package-the-content"></a>Balíček obsahu

1.  Vytvořte složku pro kopírování obsahu pro pozdější nasazení. Příklad: *C:\VSHelp*.

2.  Otevřete *cmd.exe* s oprávněními správce.

3.  Přejděte do složky, kterou jste vytvořili v kroku 1.

4.  Zadejte následující příkaz:

     `Xcopy %ProgramData%\Microsoft\HelpLibrary2 \<*foldername*>\ /y /e /k /o `

     Například: `Xcopy %ProgramData%\Microsoft\HelpLibrary2 c:\VSHelp\ /y /e /k /o`

### <a name="deploy-the-content"></a>Nasazení obsahu

1.  Vytvoření sdílené síťové složky a zkopírujte obsah nápovědy k umístění.

     Například kopírovat obsah *C:\VSHelp* k  *\\\myserver\VSHelp*.

2.  Vytvoření *.bat* soubor obsahuje skript nasazení pro obsah nápovědy. Vzhledem k tomu, že klienta pravděpodobně by mohly mít zámek pro čtení na některý ze souborů odstraňuje jako součást nabízeného oznámení, měli byste vypnout před vkládání aktualizací klienta. Příklad:

    ```
    REM - copy pre-ripped content to ProgramData
    Xcopy %~dp0HelpLibrary2 %SYSTEMDRIVE%\ProgramData\Microsoft\HelpLibrary2\ /y /e /k /o
    if ERRORLEVEL 1 ECHO *** ERROR COPYING Help Library files to ProgramData (%ERRORLEVEL%)
    ```

3.  Spustit *.bat* soubor na místní počítače, které chcete nainstalovat na obsah nápovědy.

## <a name="see-also"></a>Viz také

- [Argumenty příkazového řádku pro správce obsahu nápovědy](../ide/command-line-arguments-for-the-help-content-manager.md)
- [Přepsání Help Content Manager](../ide/help-content-manager-overrides.md)
- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)
- [Prohlížeč nápovědy sady SDK](../extensibility/internals/microsoft-help-viewer-sdk.md)