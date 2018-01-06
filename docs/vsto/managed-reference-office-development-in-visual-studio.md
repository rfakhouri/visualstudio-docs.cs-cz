---
title: "Spravovaný odkaz (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
ms.assetid: 1fa66da0-9d90-4524-ba4f-4da13aab73b5
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 04d89dee1c078ae0b27b96f2e72b25f30dc52845
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="managed-reference-office-development-in-visual-studio"></a>Spravovaný odkaz (vývoj pro Office v sadě Visual Studio)
  Tato část obsahuje referenční dokumentace rozhraní API pro obory názvů a typy, které se používají v Office projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Referenční dokumentace rozhraní API o obory názvů a typy, které se používají v projektech Office cílených na rozhraní .NET Framework 3.5, najdete v následující části odkaz v dokumentaci sady Visual Studio: [http://go.microsoft.com/fwlink/? LinkId = 160658](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 <xref:Microsoft.Office.Tools>  
 Obsahuje třídy, které jsou společné pro programování řešení pro systém Office. Mezi ně patří základní třídu pro doplňků VSTO, třídy pro vytváření vlastních podoken úloh v doplňcích VSTO, třídy pro vytváření inteligentních značek v Excelu a Wordu řešení a třídy pro vytváření podokna akcí v přizpůsobeních na úrovni dokumentu.  
  
 <xref:Microsoft.Office.Tools.Excel>  
 Obsahuje hostitelské ovládací prvky a hostitelské položky, které lze použít v řešeních pro aplikaci Excel.  
  
 <xref:Microsoft.Office.Tools.Excel.Controls>  
 Obsahuje ovládací prvky aplikace Excel a ovládací prvky Windows Forms, které lze použít v řešeních pro aplikaci Excel.  
  
 <xref:Microsoft.Office.Tools.Outlook>  
 Obsahuje třídy používané nástrojem doplňků VSTO pro Outlook, včetně třídy, které se používají k vytváření oblastí formulářů vlastní.  
  
 <xref:Microsoft.Office.Tools.Ribbon>  
 Obsahuje třídy, které se používají k úpravě prostřednictvím kódu programu vlastních nastavení pásu karet, které jsou vytvořeny pomocí Návrháře pásu karet.  
  
 <xref:Microsoft.Office.Tools.Word>  
 Obsahuje hostitelské ovládací prvky a hostitelské položky, které lze použít v řešeních pro aplikaci Word.  
  
 <xref:Microsoft.Office.Tools.Word.Controls>  
 Obsahuje ovládací prvky aplikace Word a ovládací prvky Windows Forms, které lze použít v řešeních pro aplikaci Word.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications>  
 Obsahuje <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy a sadu související s mezipamětí datových tříd. Tyto třídy můžete použít k úpravě některých aspektů přizpůsobení na úrovni dokumentu v počítačích, které nemají nainstalovanou sadu Microsoft Office.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>  
 Obsahuje <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> rozhraní (která můžete implementovat pro vytvoření *post akce nasazení* pro řešení Office), výjimky, které může být vyvolána při instalaci řešení Office a jiná rozhraní API, které jsou součástí Visual Infrastruktura Studio.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>  
 Obsahuje většinu výjimky, které může být vyvolána [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], několik tříd, které je možné data do mezipaměti v přizpůsobeních na úrovni dokumentu a jiná rozhraní API, které jsou součástí infrastruktury sady Visual Studio.  
  
 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>  
 Obsahuje třídy MSBuild úloh, které se používají k vytvoření projektů Office.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Navrhování a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  