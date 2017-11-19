---
title: "Postupy: migrace rozšiřitelnost projektů na Visual Studio 2015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio SDK, upgrading
ms.assetid: 22491cdc-8f04-4e1c-8eb4-ff33798ec792
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 016e609acb7ad837580b4cabb6055169ac7357c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-migrate-extensibility-projects-to-visual-studio-2015"></a>Postupy: migrace rozšiřitelnost projektů na Visual Studio 2015
Zde je postup upgradu rozšíření.  
  
> [!IMPORTANT]
>  Pokud máte v úmyslu spravovat z verze rozšíření řešení pro starší verze sady Visual Studio, ujistěte se, že jste vytvořili kopii před zahájením proveďte upgrade. Může být obtížné upgradovanou verzi vrátit do předchozího stavu.  
  
#### <a name="to-upgrade-an-extensibility-solution"></a>Upgradovat řešení rozšiřitelnosti  
  
1.  Použití kopie, kterou chcete upgradovat, otevřete v nové verzi. Budete informováni, že není reverzibilního upgradu.  
  
2.  Po dokončení upgradu, změňte cestu externí program na novou verzi devenv.exe. Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení**, zvolte **vlastnosti**. V **ladění** kartě, vyhledejte textového pole podle **počáteční vnějšímu programu** a změňte cestu devenv.exe Cesta sady Visual Studio 2015, která by měla vypadat přibližně takto:  
  
     **14.0\Common7\IDE\devenv.exe %ProgramFiles%\Microsoft visual Studio**  
  
3.  Přidáte odkaz na Microsoft.VisualStudio.Shell.14.0.dll. (Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a potom zvolte **přidat / Reference**. Vyberte **rozšíření** kartě a potom zkontrolujte **Microsoft.VisualStudio.Shell.14.0**.)  
  
4.  Sestavte řešení. Vytvořené soubory se nasadí do:  
  
     **%LOCALAPPDATA%\Microsoft\VisualStudio.14.0Exp\Extensions\\< vytvářet název\>\\< název projektu\>\\< projektu verze\> \\** .  
  
#### <a name="to-update-an-extensibility-project-to-nuget-vs-sdk-reference-assemblies"></a>K aktualizaci projektu rozšíření NuGet VS SDK referenční sestavení  
  
1.  Určete referenční sestavení VS SDK, které je třeba projekt.  V **Průzkumníku řešení**, rozbalte položku projektu **odkazy** uzel a projděte si seznam odkazů na projekty.  Odkazy na sestavení VS SDK bude mít předponu **Microsoft.VisualStudio** v názvu (například: Microsoft.VisualStudio.Shell.14.0).  
  
2.  Odebrat odkaz na sestavení VS SDK z projektu jejich výběrem, klikněte pravým tlačítkem a **odebrat**.  
  
3.  Přidejte verze NuGet referenční sestavení VS SDK.  Stále v **odkazy na Průzkumníka řešení** uzlu, otevřete **spravovat balíčky NuGet...**  dialogové okno.  Pokud chcete získat další informace o tomto dialogovém okně, přečtěte si téma [uživatelského rozhraní Správce balíčků](http://docs.microsoft.com/NuGet/Tools/Package-Manager-UI). Referenční sestavení VS SDK jsou publikovány na [nuget.org](http://www.nuget.org) podle [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility).  
  
4.  Pomocí **nuget.org** jako vaše **zdroj balíčku**, vyhledejte název balíčku NuGet, který by odpovídal požadované referenční sestavení (například: Microsoft.VisualStudio.Shell.14.0) a nainstalujte ho v vaší projekt.  NuGet může přidat více referenční sestavení splníte závislosti počáteční sestavení.  
  
     Pokud dáváte přednost, můžete přidat všechny referenční sestavení VS SDK najednou nainstalováním VS SDK [Meta balíček](http://www.nuget.org/packages/VSSDK_Reference_Assemblies).  
  
5.  Můžete také přejít k používání NuGet verzi nástroje pro sestavení VS SDK. Tento balíček NuGet je [Microsoft.VSSDK.BuildTools](http://www.nuget.org/packages/Microsoft.VSSDK.BuildTools) a jednou přidat k projektu bude obsahovat potřebné nástroje a cílové soubory k vám umožní vytvořit projekt rozšíření v počítači bez VS SDK nainstalovat.  
  
> [!NOTE]
>  Není nutné aktualizovat existující projekty rozšiřitelnosti, aby používaly NuGet referenční sestavení a nástroje.  Může i dál sestavení pomocí referenční sestavení a nástroje, které jsou nainstalované s VS SDK.