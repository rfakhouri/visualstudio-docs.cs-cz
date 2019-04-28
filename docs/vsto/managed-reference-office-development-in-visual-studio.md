---
title: Spravovaný odkaz (vývoj pro Office v sadě Visual Studio)
ms.date: 02/02/2017
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
ms.openlocfilehash: f8ff9a196fb459359502e4c9f8599fbdeff3e1ce
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438796"
---
# <a name="managed-reference-office-development-in-visual-studio"></a>Spravovaný odkaz (vývoj pro Office v sadě Visual Studio)
  Tato část obsahuje referenční dokumentaci rozhraní API pro obory názvů a typy, které se používají v sadě Office projekty, které cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Referenční dokumentace rozhraní API o obory názvů a typy, které se používají v projektech Office cílených rozhraní .NET Framework 3.5, najdete v následující informační části v dokumentaci k sadě Visual Studio: [ http://go.microsoft.com/fwlink/?LinkId=160658 ](http://go.microsoft.com/fwlink/?LinkId=160658).

> [!NOTE]
> Zajímá vás vývoj řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na nové [Office Add-ins modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky sady Office mají malé náklady v porovnání s doplňky VSTO a řešení a je můžete vytvořit s využitím téměř jakékoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.

## <a name="in-this-section"></a>V tomto oddílu
 <xref:Microsoft.Office.Tools>

 Obsahuje třídy, které jsou společné pro programování řešení pro systém Office. Patří mezi základní třídu pro doplňky VSTO, tříd pro vytvoření vlastních podoken úloh v doplňcích VSTO, třídy pro vytváření inteligentních značek v Excelu a Wordu řešení a tříd pro vytvoření podoken akcí v přizpůsobeních na úrovni dokumentu.

 <xref:Microsoft.Office.Tools.Excel>

 Obsahuje ovládací prvky hostitele a hostitelské položky, které lze použít v řešeních pro aplikaci Excel.

 <xref:Microsoft.Office.Tools.Excel.Controls>

 Obsahuje ovládací prvky Excelu a ovládací prvky Windows Forms, které lze použít v řešeních pro aplikaci Excel.

 <xref:Microsoft.Office.Tools.Outlook>

 Obsahuje třídy používané doplňků VSTO pro Outlook, včetně tříd, které se používají k vytváření oblastí formulářů vlastní.

 <xref:Microsoft.Office.Tools.Ribbon>

 Obsahuje třídy, které umožňují programově změnit vlastních nastavení pásu karet, které jsou vytvořeny pomocí Návrháře pásu karet.

 <xref:Microsoft.Office.Tools.Word>

 Obsahuje ovládací prvky hostitele a hostitelské položky, které lze použít v řešeních pro aplikaci Word.

 <xref:Microsoft.Office.Tools.Word.Controls>

 Obsahuje ovládací prvky aplikace Word a ovládací prvky Windows Forms, které lze použít v řešeních pro aplikaci Word.

 <xref:Microsoft.VisualStudio.Tools.Applications>

 Obsahuje <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy a sadu související s mezipamětí datových tříd. Tyto třídy můžete použít k úpravě některých aspektů přizpůsobení na úrovni dokumentu v počítačích, které nemají nainstalovanou sadu Microsoft Office.

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>

 Obsahuje <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> rozhraní (která můžete implementovat pro vytvoření *nasazení akce odeslání* pro řešení Office), výjimky, které mohou být vyvolány při instalaci řešení pro Office a další rozhraní API, které jsou součástí Vizuálu Studio infrastruktury.

 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>

 Obsahuje většinu výjimek, které mohou být vyvolány [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], několik tříd, které je možné ukládat data do mezipaměti v přizpůsobeních na úrovni dokumentu a jiná rozhraní API, které jsou součástí infrastruktury sady Visual Studio.

 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>

 Obsahuje třídy úlohy MSBuild, které se používají k sestavení projektů Office.

## <a name="see-also"></a>Viz také:
- [Visual Studio tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Ukázky vývoje pro Office a názorné postupy](../vsto/office-development-samples-and-walkthroughs.md)
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
