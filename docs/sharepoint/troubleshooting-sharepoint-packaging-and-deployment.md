---
title: Řešení potíží s balení a nasazení SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.WorkflowDeployment.Troubleshooting
- VS.SharePointTools.Project.PackageRetraction
- VS.SharePointTools.Deployment.Troubleshooting
- VS.SharePointTools.Deploying.Troubleshooting
- VS.SharePointTools.Project.DeploymentTroubleshooting
- VS.SharePointTools.Project.SharePointNotInstalled
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packaging
- SharePoint development in Visual Studio, troubleshooting
- SharePoint development in Visual Studio, deployment conflict resolution
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3228bcea89bbc03c218f31de86357cf1c193f569
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237585"
---
# <a name="troubleshooting-sharepoint-packaging-and-deployment"></a>Řešení potíží s balením a nasazením služby SharePoint

Toto téma popisuje různé problémy, které se můžete setkat při zabalení a nasazení řešení služby SharePoint.

## <a name="enabling-enhanced-debugging"></a>Povolení rozšířeného ladění
 Při diagnostice mezi další vrstvy, SharePoint a Visual Studio, můžete pomocí klíče registru EnableDiagnostics zobrazíte trasování zásobníku. Další informace najdete v tématu [ladění řešení služby SharePoint](../sharepoint/debugging-sharepoint-solutions.md).

## <a name="adding-project-output-to-the-solution-package"></a>Přidání výstupu projektu do balíčku řešení
 Výstup projektu můžete přidat do balíčku pomocí návrháře balíčků. Při přidání výstupu projektu @, ale ujistěte, že platformy projektu odpovídá platforma řešení služby SharePoint. Doporučujeme vám, že používáte **libovolný procesor** Cílová platforma pro sestavení, které chcete nasadit na server služby SharePoint. Další informace najdete v tématu [stránka kompilovat, Návrhář projektu &#40;jazyka Visual Basic&#41; ](../ide/reference/compile-page-project-designer-visual-basic.md) a [Advanced kompilátoru dialogové okno nastavení &#40;jazyka Visual Basic&#41;](../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md).

## <a name="validation-warnings-and-errors"></a>Upozornění a chyby při ověřování
 Nástroje pro vývoj pro SharePoint v sadě Visual Studio kroků ověření ověřte, zda je správně vytvořen balíčku řešení. Můžete také vytvořit vlastní ověření kroky pro funkce a balíčky. Další informace najdete v tématu [postupy: vytvoření vlastní funkce a pravidel ověřování balíčku pro řešení služby SharePoint](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).

## <a name="deployment-conflict-resolution"></a>Řešení konfliktů při nasazení
 Když nasadíte řešení služby SharePoint, můžete zjistit kolize, když položky na serveru má stejný název, URL nebo ID jako položka v balíčku vaše řešení. Můžete změnit **řešení konfliktů při nasazení** vlastnost řešení, sestavy, nebo můžete ignorovat kolizí pro moduly, webové části, seznam instancí a typy obsahu.

 Následující tabulka ukazuje nastavení **řešení konfliktů při nasazení** vlastnost.

|Hodnota|Popis|
|-----------|-----------------|
|Automatické|Zjistí kolize a řeší konflikty automaticky.|
|řádku|Zjistí kolize a ohlásí je vývojář před řešení konfliktů.|
|Žádné|Nezjistí kolizí.|

## <a name="differences-between-f5-deployment"></a>Rozdíly mezi nasazením pomocí klávesy F5

Pokud používáte Visual Studio k nasazení projektu služby SharePoint na místním serveru SharePoint pro testování a ladění, nejsou některé další kroky, které se provádí pomocí sady Visual Studio.

1.  Během kroku nasazení resetujte Internetové informační služby (IIS).

2.  Automaticky přidružte pracovní postupy.

3.  Nastavení funkce aktivace pořadí podle hierarchie v Návrháři balíčku.

Můžete přidat vlastní nasazení postup další změny chování F5. Další informace najdete v tématu [návod: vytvoření vlastní krok nasazení pro projekty SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).

## <a name="delay-displaying-sharepoint-page-when-deploying-visual-web-part"></a>Prodleva zobrazení stránky služby SharePoint při nasazení vizuální webové části

Trvá moc dlouho se objeví při nasazování do složky Bin Visual webovou část na stránku služby SharePoint [!INCLUDE[wiprlhext](../sharepoint/includes/wiprlhext-md.md)], [!INCLUDE[win7](../sharepoint/includes/win7-md.md)], nebo [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)]. Pokud se změní soubory ve nejvyšší úrovni [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] znovu zkompiluje celý webové aplikace directory, jako je například adresáře Bin. To může způsobit zpoždění až 25 sekund pro stránku služby SharePoint k vykreslení.

### <a name="error-message"></a>Chybová zpráva
 Žádné

### <a name="resolution"></a>Rozlišení
 Chcete-li tento problém obejít, postupujte takto:

1.  Nainstalujte aktualizaci KB967535, jak je uvedeno v článek Microsoft Support [OPRAVTE: opravu hotfix je k dispozici k řešení problémů s dvě technologie ASP.NET ve službě IIS 7.0 pro systém Windows Vista a Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=179055).

2.  Přidejte následující řádek v souboru Web.config:

    ```xml
    <compilation batch="false" optimizeCompilations="true">
    ```

## <a name="sharepoint-project-deployment-fails-with-error-failed-to-extract-the-cab-file-in-the-solution"></a>Nasazení projektu SharePoint se nezdaří s chybou „Nepodařilo se vyextrahovat soubor CAB v rámci řešení“
 Pokud název všechny položky projektu služby SharePoint obsahuje závorky, jeho řešení selže v nasazení s chybou.

### <a name="error-message"></a>Chybová zpráva
 V kroku nasazení přidat řešení došlo k chybě: Nepodařilo se extrahovat soubor cab v řešení.

### <a name="resolution"></a>Rozlišení
 Chcete-li tento problém obejít, odstraňte všechny závorky v názvech položek projektu služby SharePoint.

## <a name="error-appears-when-deploying-a-visual-web-part-to-a-site-on-a-different-web-application"></a>Při nasazení vizuální webové části na web jiné webové aplikace se zobrazí chyba
 Při prvním nasazení visual webové části na web na webovou aplikaci, než ten, na kterém je aktuálně nasazená (změnou vlastnost SiteUrl visual webovou část), dojde k chybě.

### <a name="error-message"></a>Chybová zpráva
 V kroku nasazení přidat řešení došlo k chybě: v této farmě již byla nainstalována funkce s ID [#]. Použijte atribut vynucené explicitně znovu nainstalovat funkci.

### <a name="resolution"></a>Rozlišení
 K této chybě dojde v důsledku způsob, jakým visual funkce webových částí jsou odvolán ve službě SharePoint. Pro úspěšné nasazení webové části visual, znovu nasaďte řešení tak, že zvolíte klávesy F5.

## <a name="warning-appears-when-deploying-nested-user-controls"></a>Při nasazení vnořených uživatelských ovládacích prvků se zobrazí upozornění
 Toto upozornění se zobrazí, když nasadíte řešení služby SharePoint, který má vnořené uživatelské ovládací prvky, jako je například visual webovou část, který obsahuje uživatelský ovládací prvek nebo uživatelský ovládací prvek, který obsahuje vizuální webové části nebo jiný uživatelský ovládací prvek. Toto upozornění se zobrazí, jestli je přidání ovládacího prvku do návrháře přetažením z panelu nástrojů nebo pomocí @Register direktivy v zobrazení zdroje.

### <a name="error-message"></a>Chybová zpráva
 Upozornění 1 elementu ' [*název ovládacího prvku*] "není známá element. Tato situace může nastat, pokud dochází k chybě kompilace na webu nebo v souboru web.config není k dispozici.

### <a name="resolution"></a>Rozlišení
 Pokud systém projektu sady Visual Studio nemá informace o vnořené uživatelský ovládací prvek, nemůže poskytnout IntelliSense a jeho vydá upozornění. Systém projektu ne vnořené uživatelského ovládacího prvku Pokud projekt není sestaven a návrháře není zavřete a znovu otevřete, nebo pokud automaticky odvolat možnost povolena, což způsobí, že uživatelského ovládacího prvku na odvolat z podregistru služby SharePoint po ladění.

 Pokud chcete odebrat toto upozornění, buď sestavte projekt a pak zavřete a znovu návrháře nebo zakázat automaticky odvolat možnost pro projekt. Chcete-li to provést, zrušte **automaticky odvolat po ladění** políčko **SharePoint** kartě dialogové okno Vlastnosti projektu.

## <a name="see-also"></a>Viz také:

- [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)