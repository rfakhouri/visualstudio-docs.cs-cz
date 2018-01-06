---
title: "Upgrade a migrace řešení Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], upgrading
- Office projects [Office development in Visual Studio], upgrading
- upgrading applications [Office development in Visual Studio]
- upgrading Office solutions in Visual Studio
- migrating Office solutions in Visual Studio
ms.assetid: cc60cdcb-593d-498a-8358-f1f3ac673fe1
caps.latest.revision: "105"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fd6ff05fde0e02e9b45b67ffe665a296085bf934
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="upgrading-and-migrating-office-solutions"></a>Upgradování a migrace řešení pro systém Office
  Pokud máte aplikaci Microsoft Office project, která byla vytvořena ve starší verzi sady Visual Studio, je třeba upgradovat projekt, který používá v aktuální verzi sady Visual Studio. Pokud chcete upgradovat aplikaci Microsoft Office project, otevřete ho ve verzi Visual Studia, která zahrnuje nástroje Microsoft Office developer tools. Další informace o verzích sady Visual Studio, které zahrnují nástroje Microsoft Office developer tools najdete v tématu [konfigurace počítače pro vývoj řešení pro Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
> [!NOTE]  
>  Visual Studio nemůže upgradovat InfoPath formuláře šablony projektů, které byly vytvořeny pomocí předchozí verze sady Visual Studio. Tyto typy projektů nejsou podporovány v aktuální verzi sady Visual Studio.  
  
## <a name="changes-to-upgraded-projects"></a>Změny v upgradovaných projektů  
 Při upgradu na projekt aplikace Microsoft Office Visual Studio upraví projektu pro následující položky:  
  
-   Sadu Visual Studio 2010 Tools for Office Runtime. Další informace najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
-   Aktuální odkazy na sestavení.  
  
-   Verze rozhraní .NET Framework, kterou podporuje typ projektu (při upgradu na sadu Visual Studio 2013 pouze).  
  
-   Verze systému Microsoft Office, kterou podporuje typ projektu (při upgradu na sadu Visual Studio 2013 pouze).  
  
## <a name="assembly-references"></a>Odkazy na sestavení  
 Visual Studio upgraduje následující odkazy na sestavení v projektu:  
  
-   Aplikace Microsoft Office primární spolupracující sestavení (PIA).  
  
-   Sestavení v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Další informace o těchto sestavení najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
-   Nové nebo aktualizované verze závislého sestavení.  
  
## <a name="targeted-net-framework"></a>Cílové rozhraní .NET Framework  
 Při upgradu na projekt na Visual Studio 2013, Visual Studio upraví projekt, který má cílit buď [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] nebo [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Verze rozhraní .NET framework, který je cílem projektu závisí na jaká verze systému Office je nainstalován v počítači. Pokud [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] je nainstalovaná, Visual Studio upraví projekt k cíli [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Jinak, Visual Studio upraví projekt k cíli [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
> [!NOTE]  
>  Možná budete muset provést některé další kroky pro spuštění přesměrovanou řešení pro vývoj a počítače koncového uživatele a projekt nebudou nadále kompilovány, pokud používá některých funkcí. Další informace najdete v tématu [migrace řešení pro systém Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
 Pokud cílíte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později v projektech Office, můžete použít některé funkce, které nejsou k dispozici, pokud cílíte na rozhraní .NET Framework 3.5. Další informace najdete v tématu [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
## <a name="targeted-office-application"></a>Aplikace cílené Office  
 Při upgradu Microsoft Office project na Visual Studio 2013, Visual Studio upravuje projekt cílení na verzi aplikace Microsoft Office podporovaný typ projektu, například přizpůsobení na úrovni dokumentu projektu nebo projektu doplňku VSTO.  
  
 Projekty Office v sadě Visual Studio 2013, můžete vybrat [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] aplikace. Visual Studio upravuje projekt, který má mít nejnovější verzi systému office, který jste nainstalovali. Pokud žádná z těchto verzí systému Office jsou nainstalovány, neupgraduje projektu sady Visual Studio.  
  
> [!NOTE]  
>  Pokud upgradujete projektu doplňku VSTO cíl [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] nebo novější, ujistěte se, že `ThisAddIn_Startup` obslužné rutiny události Add-in VSTO neobsahuje kód, který má přístup k dokumentu v aplikaci. Další informace najdete v tématu [přístup k dokumentu při Office spuštěním aplikace](../vsto/programming-vsto-add-ins.md#AccessingDocuments).  
  
 Pro úpravy na úrovni dokumentů [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] převede dokumenty v projektu, které mají binární formát, jako jsou dokumenty, které mají příponu .xls nebo .doc na formát Office Open XML. Další informace o Open XML, najdete v části [Úvod do nové přípony názvů souborů a formáty Open XML](https://support.office.com/en-nz/article/Introduction-to-new-file-name-extensions-eca81dcb-5626-4e5b-8362-524d13ae4ec1).  
  
> [!NOTE]  
>  Inteligentní značky nepoužívají v aplikaci Excel 2010 a Word 2010. Proto pokud řešení používá inteligentní značky, musíte je odstranit před testování a ladění v sadě Visual Studio 2013 nebo Visual Studio 2015.  
  
## <a name="upgrading-microsoft-office-2003-projects"></a>Upgrade projektů Microsoft Office 2003  
 Existují některé další aspekty pro upgrade přizpůsobení na úrovni dokumentu a doplňků VSTO cílených Microsoft Office 2003.  
  
### <a name="document-level-projects"></a>Projekty na úrovni dokumentu  
 Pokud dokument v projektu obsahuje ovládací prvky Windows Forms, musí také mít Visual Studio 2005 Tools pro druhý edice modul Runtime sady Office nainstalována před upgradem projektu. Pokud tuto verzi modulu runtime není nainstalována na vývojovém počítači, před provedením upgradu na projekt, upgradovaném projektu může obsahovat kompilace nebo chyby runtime. Po dokončení upgradu na projekt, můžete odinstalovat sadu Visual Studio 2005 Tools for Office Runtime druhý edici z vývojovém počítači Pokud není používán pomocí jiných řešení pro Office. Je k dispozici jako distribuovatelného balíčku z Microsoft Download Center v této verzi modulu runtime [Microsoft Visual Studio 2005 Tools pro druhý edice modul Runtime sady Office (VSTO 2005 SE) (x86)](http://go.microsoft.com/fwlink/?linkid=49612).  
  
### <a name="vsto-add-in-projects"></a>Projekty doplňku VSTO  
 Pokud soubor řešení pro svůj projekt původní zahrnuty projektu instalace nebo InstallShield Limited Edition, která byla nakonfigurována pro instalaci doplňku VSTO, Visual Studio upgraduje projektu, ale neprovede žádné další změny do projektu. Pokud chcete používat k nasazení vašeho doplňku VSTO soubor Instalační služby systému Windows, musíte upravit projektu instalace nebo InstallShield Limited Edition k instalaci nové požadavky, jako [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], pro systém Office Runtime a volitelně nástrojů pro Visual Studio 2010 Primární spolupracující sestavení odkazuje vaší doplňku VSTO. Další informace najdete v tématu [nasazení řešení Office pomocí Instalační služba systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
 Pokud chcete použít ClickOnce k nasazení vašeho doplňku VSTO, můžete zcela odstranit projektu instalace nebo InstallShield Limited Edition. Další informace o nasazení doplňků VSTO s použitím technologie ClickOnce najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: upgradování řešení Office](http://msdn.microsoft.com/en-us/a269e539-b717-4680-a568-2152b070347e)   
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Upgrade projektu, dialogové okno Možnosti](../vsto/project-upgrade-options-dialog-box.md)  
  
  