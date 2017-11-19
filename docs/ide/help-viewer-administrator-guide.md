---
title: "Příručka správce Help Vieweru | Microsoft Docs"
ms.custom: 
ms.date: 11/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4340c69f-b96b-4932-bb82-38b16a5ab149
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3c4c034b6aec75499d2e38af35f22cd852fa2e15
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="help-viewer-administrator-guide"></a>Příručka správce Help Viewer
Help Viewer umožňuje spravovat místní instalace nápovědy pro sítě v prostředích s nebo bez připojení k Internetu. Místní obsah nápovědy je konfigurováno na základě na počítač. Ve výchozím nastavení uživatelé musí mít práva správce k jejich místní Nápověda instalace aktualizace.  
  
Pokud vaše síťové prostředí umožňuje klientům přístup k Internetu, můžete použít Správce obsahu nápovědy spustitelný soubor pro nasazení obsahu místní nápovědu z Internetu. Další informace o HlpCtntMgr.exe syntaxe příkazového řádku najdete v tématu [argumenty příkazového řádku pro správce obsahu nápovědy](../ide/command-line-arguments-for-the-help-content-manager.md).

Informace o vytváření obsahu, vytvoří koncový bod služby intranetu a podobné typy aktivit, najdete v článku [pomoci SDK prohlížeč](../extensibility/internals/microsoft-help-viewer-sdk.md).  
  
Pokud nemají přístup k Internetu v síťovém prostředí, Prohlížeč nápovědy můžete nasadit místního obsahu nápovědy z intranetu nebo sdílené síťové složce. Nápověda k sadě Visual Studio IDE možnosti lze zakázat i pomocí [klíč registru přepsání](../ide/help-content-manager-overrides.md) pro funkce, jako:

- online a offline nápovědy

- Instalace obsahu při prvním spuštění rozhraní IDE

- určení obsahu služby intranetu

- Správa obsahu 
  
## <a name="deploying-local-help-content-from-the-internet"></a>Nasazení místního obsahu nápovědy z Internetu  
Pomůže obsah Manager (HlpCtntMgr.exe) můžete použít k nasazení místního obsahu nápovědy z Internetu do klientských počítačů. Použijte následující syntaxi:  
  
```
\\%ProgramFiles(x86)%\Microsoft Help Viewer\v2.3\HlpCtntmgr.exe /operation \<*name*> /catalogname \<*catalog name*> /locale \<*locale*>
```
  
Další informace o HlpCtntMgr.exe syntaxe příkazového řádku najdete v tématu [argumenty příkazového řádku pro správce obsahu nápovědy](../ide/command-line-arguments-for-the-help-content-manager.md).  
  
Požadavky:  
  
-   Klientské počítače musí mít přístup k Internetu.  
  
-   Uživatelé musí mít oprávnění správce k aktualizaci, přidat nebo odebrat místní obsah nápovědy, co byla nainstalována.  
  
 Upozornění:  
  
-   Zdroj výchozího nápovědy bude stále online.
  
### <a name="example"></a>Příklad  
Následující příklad nainstaluje anglickou obsah pro sadu Visual Studio ke klientskému počítači.  
  
##### <a name="to-install-english-content-from-the-internet"></a>Chcete-li nainstalovat anglickou obsah z Internetu  
  
1.  Zvolte **spustit** a potom zvolte **spustit**.  
  
2.  Zadejte následující příkaz:  
  
     C:\Program soubory (x86) \Microsoft Help Viewer\v2.3\hlpctntmgr.exe /operation nainstalovat /catalogname VisualStudio15 /locale en-us  
  
3.  Stiskněte klávesu **zadejte**.  
  
## <a name="deploying-pre-installed-local-help-content-on-client-computers"></a>Nasazení předem nainstalovaná místní obsah nápovědy na klientských počítačích
Můžete nainstalovat sadu obsahu z online k jednomu počítači a poté zkopírujte tuto nainstalovanou sadu obsahu do jiných počítačů.  
  
Požadavky:  
  
-   Počítač, na kterém instalujete sadu obsahu, který se musí mít přístup k Internetu.  
  
-   Uživatelé musí mít oprávnění správce k aktualizaci, přidat nebo odebrat místní obsah nápovědy, co byla nainstalována.  
  
    > [!TIP]
    >  Pokud uživatelé nemají oprávnění správce, doporučujeme zakázat kartě Správa obsahu v okně nápovědy. Další informace najdete v tématu [pomoci správce obsahu přepsání](../ide/help-content-manager-overrides.md).  
  
Upozornění:
  
-   Zdroj výchozího nápovědy bude stále online.
  
### <a name="create-the-content-set"></a>Vytvořit sadu obsahu  
Před vytvořením základní sady obsahu, musíte nejprve odinstalovat všechny místní obsah sady Visual Studio na cílovém počítači.  
  
#### <a name="to-uninstall-local-help"></a>Chcete-li odinstalovat místní Nápověda  
  
1.  V okně nápovědy, vyberte **spravovat obsah** kartě.  
  
2.  Přejděte do dokumentu sady Visual Studio.  
  
3.  Zvolte **odebrat** vedle jednotlivých podřízených položek.  
  
4.  Zvolte **aktualizace** odinstalovat.
  
5.  %ProgramData%\Microsoft\HelpLibrary2\Catalogs\VisualStudio15 a ověřte, že složka obsahuje pouze catalogType.xml souboru.  
  
 Odebraný všechny dříve nainstalované místní Visual Studio obsahu nápovědy budete chtít stáhnout základní sady obsahu.  
  
#### <a name="to-download-the-content"></a>Ke stažení obsahu  
  
1.  V okně nápovědy, vyberte **spravovat obsah** kartě.  
  
2.  V části **doporučená dokumentaci** nebo **dostupnou dokumentaci**, přejděte do dokumentace sad, které chcete stáhnout a potom zvolte **přidat**.  
  
3.  Zvolte **aktualizace**.  
  
 Dále musíte balíčku obsahu, aby se dala nasadit do klientských počítačů.  
  
#### <a name="to-package-the-content"></a>Balíček obsahu  
  
1.  Vytvořte složku pro kopírování obsahu pro pozdější nasazení. Příklad: C:\VSHelp.  
  
2.  Otevřete cmd.exe s oprávněními správce.  
  
3.  Přejděte do složky, kterou jste vytvořili v kroku 1.  
  
4.  Zadejte následující příkaz:  
  
     Xcopy %ProgramData%\Microsoft\HelpLibrary2 \< *název_složky*> \ /y /e /k /o  
  
     Například:`Xcopy %ProgramData%\Microsoft\HelpLibrary2 c:\VSHelp\ /y /e /k /o`  
  
### <a name="deploying-the-content"></a>Nasazení obsahu  
  
#### <a name="to-deploy-the-content"></a>K nasazení obsahu  
  
1.  Vytvoření sdílené síťové složky a zkopírujte obsah nápovědy k umístění.  
  
     Například kopírovat obsah C:\VSHelp k \\\myserver\VSHelp.  
  
2.  Vytvořte soubor .bat tak, aby obsahovala skript nasazení pro obsah nápovědy. Vzhledem k tomu, že klienta pravděpodobně by mohly mít zámek pro čtení na některý ze souborů odstraňuje jako součást nabízeného oznámení, měli byste vypnout před vkládání aktualizací klienta. Příklad:  
  
    ```  
    REM - copy pre-ripped content to ProgramData  
    Xcopy %~dp0HelpLibrary2 %SYSTEMDRIVE%\ProgramData\Microsoft\HelpLibrary2\ /y /e /k /o  
    if ERRORLEVEL 1 ECHO *** ERROR COPYING Help Library files to ProgramData (%ERRORLEVEL%)
    ```  
  
3.  Spusťte soubor .bat na místní počítače, které chcete nainstalovat na obsah nápovědy.  
  
## <a name="see-also"></a>Viz také
[Argumenty příkazového řádku pro aplikaci Help Content Manager](../ide/command-line-arguments-for-the-help-content-manager.md)  
[Přepsání Help Content Manager](../ide/help-content-manager-overrides.md)  
[Microsoft Help Viewer](../ide/microsoft-help-viewer.md)  
[Prohlížeč nápovědy sady SDK](../extensibility/internals/microsoft-help-viewer-sdk.md)