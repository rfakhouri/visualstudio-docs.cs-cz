---
title: Spravované referenční materiály (vývoj pro Office v sadě Visual Studio)
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: da10833f8340d5308321038bb0500ca8408b40bb
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551766"
---
# <a name="managed-reference-office-development-in-visual-studio"></a>Spravované referenční materiály (vývoj pro Office v sadě Visual Studio)
  Tato část obsahuje referenční dokumentaci rozhraní API pro obory názvů a typy, které se používají v projektech [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] Office, [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]které cílí na nebo. Referenční dokumentace k rozhraní API pro obory názvů a typy, které se používají v projektech Office cílených na .NET Framework 3,5 naleznete v následující referenční části v dokumentaci k sadě [http://go.microsoft.com/fwlink/?LinkId=160658](http://go.microsoft.com/fwlink/?LinkId=160658)Visual Studio:.

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="in-this-section"></a>V tomto oddílu
 <xref:Microsoft.Office.Tools>

 Obsahuje třídy společné pro programování řešení pro systém Office. Patří mezi ně základní třída pro doplňky VSTO, třídy pro vytváření vlastních podoken úloh v doplňcích VSTO, třídy pro vytváření inteligentních značek v aplikacích Excel a Word a třídy pro vytváření podoken akcí v přizpůsobeních na úrovni dokumentu.

 <xref:Microsoft.Office.Tools.Excel>

 Obsahuje ovládací prvky hostitele a hostitelské položky, které lze použít v řešeních pro aplikaci Excel.

 <xref:Microsoft.Office.Tools.Excel.Controls>

 Obsahuje ovládací prvky aplikace Excel a model Windows Forms ovládací prvky, které lze použít v řešeních pro aplikaci Excel.

 <xref:Microsoft.Office.Tools.Outlook>

 Obsahuje třídy, které jsou používány doplňky VSTO pro Outlook, včetně tříd, které se používají k vytváření vlastních oblastí formuláře.

 <xref:Microsoft.Office.Tools.Ribbon>

 Obsahuje třídy, které slouží k programové úpravě přizpůsobení pásu karet vytvořeného pomocí Návrháře pásu karet.

 <xref:Microsoft.Office.Tools.Word>

 Obsahuje ovládací prvky hostitele a hostitelské položky, které lze použít v řešeních pro aplikaci Word.

 <xref:Microsoft.Office.Tools.Word.Controls>

 Obsahuje ovládací prvky aplikace Word a model Windows Forms ovládací prvky, které lze použít v řešeních pro aplikaci Word.

 <xref:Microsoft.VisualStudio.Tools.Applications>

 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Obsahuje třídu a sadu souvisejících datových tříd uložených v mezipaměti. Tyto třídy lze použít k úpravě některých aspektů přizpůsobení na úrovni dokumentu na počítačích, které nemají nainstalované systém Microsoft Office.

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>

 Obsahuje rozhraní (které můžete implementovat pro vytvoření *akce po nasazení* pro řešení Office), výjimky, které mohou být vyvolány při instalaci řešení Office a dalších rozhraní API, která jsou součástí infrastruktury sady Visual Studio. <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction>

 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>

 Obsahuje většinu výjimek, které mohou být vyvolány [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], několik tříd, které lze použít k ukládání dat do mezipaměti v přizpůsobení na úrovni dokumentu a dalších rozhraní API, která jsou součástí infrastruktury sady Visual Studio.

 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>

 Obsahuje třídy úloh nástroje MSBuild, které slouží k sestavování projektů Office.

## <a name="see-also"></a>Viz také:
- [Přehled nástrojů Visual Studio Tools for Office runtime](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [Začínáme &#40;s vývojem pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Ukázky a návody pro vývoj pro Office](../vsto/office-development-samples-and-walkthroughs.md)
- [Návrh a tvorba řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
