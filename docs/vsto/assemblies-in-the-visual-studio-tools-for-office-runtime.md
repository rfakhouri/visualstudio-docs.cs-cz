---
title: "Sestavení v sadě Visual Studio Tools for Office Runtime | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, assemblies
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 22750553e714c0aa02577ee95753e7d5b2bf13f4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="assemblies-in-the-visual-studio-tools-for-office-runtime"></a>Sestavení v nástrojích Visual Studio Tools for Office runtime
  Když vytvoříte projekt Office, Visual Studio automaticky přidá reference na [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] sestavení, které se používají pro typ projektu a cílové rozhraní .NET Framework projektu. V rozšíření Office pro rozhraní .NET Framework 3.5, existují různé sestavení [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], a [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Další informace o rozšířeních Office, najdete v části [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-4-and-the-includenetv45vstoincludesnet-v45-mdmd"></a>Sestavení v Office rozšíření pro rozhraní .NET Framework 4 a[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 Následující tabulka uvádí sestavení, které jsou součástí Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Dokumentaci o obory názvů a typy v těchto sestavení najdete v tématu [spravované odkaz & #40; vývoj pro Office v sadě Visual Studio & #41;](../vsto/managed-reference-office-development-in-visual-studio.md).  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.dll|Poskytuje následující typy:<br /><br /> -Typy pro vytváření vlastních nastavení pásu karet a inteligentní značky. **Poznámka:** inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Typy pro vytvoření podokna akcí v přizpůsobeních na úrovni dokumentu a vlastních podoken úloh v doplňků VSTO.|  
|Microsoft.Office.Tools.Excel.dll|Poskytuje rozhraní, které představují hostitelských položek a hostitelských ovládacích prvků pro projekty aplikace Excel a podpůrné typy. Další informace najdete v tématu [automatizace aplikace Excel pomocí rozšířených objekty](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.dll|Obsahuje typy, které můžete použít k vytvoření vlastního formuláře oblasti v doplňků VSTO pro Outlook.|  
|Microsoft.Office.Tools.Word.dll|Poskytuje rozhraní, které představují hostitelských položek a hostitelských ovládacích prvků pro projekty aplikace Word a podpůrné typy. Další informace najdete v tématu [automatizace aplikace Word pomocí rozšířených objekty](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v4.0.Framework.dll|Poskytuje následující typy:<br /><br /> -Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Atributy, které můžete použít při vytváření aplikace Outlook formuláři oblasti.|  
|Microsoft.Office.Tools.dll|Obsahuje typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut a <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> rozhraní, které můžete použít k mezipaměti datové objekty v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).<br />-Na <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> rozhraní, které můžete implementovat, abyste spusťte další instalační kroky jako poslední krok ClickOnce instalační program pro řešení Office. Další informace najdete v tématu [nasazení řešení Office aplikací ClickOnce pomocí](../vsto/deploying-an-office-solution-by-using-clickonce.md).<br />-Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy, které můžete použít k přizpůsobení sestavení připojení k dokumentům a přístup k data uložená v mezipaměti v dokumentech. Další informace najdete v tématu [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Několik tříd, které představují hierarchii do mezipaměti data v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|  
  
 Projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] také odkazují následující sestavení. Tyto sestavení nejsou součástí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] redistributable. Místo toho jsou závislé sestavení, které musí být nasazené s vaším řešením. Ve výchozím nastavení, se kopírují do výstupní složky sestavení projektu ( **místní kopie** vlastnost pro tyto sestavení jsou nastavena na **True**). Pokud nasadíte projektu s použitím technologie ClickOnce, jsou tyto sestavení součástí vygenerovaný balíček.  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|Poskytuje základní třídy pro generovaný objekt `ThisAddIn` třídy v projekty doplňku VSTO a generovaná třída pásu karet ve všech projektech.|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|Poskytuje následující typy:<br /><br /> -Základní třídy pro generovaný objekt `ThisWorkbook` a `Sheet` třídy v úrovni dokumentu projekty pro aplikaci Excel.<br />– Ovládací prvky Windows Forms, které můžete použít na listech v projekty aplikace Excel.|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Poskytuje základní třídy pro generovaný objekt `ThisAddIn` a třídy oblastí formulářů v projektech Outlook.|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|Poskytuje následující typy:<br /><br /> -Základní třídy pro generovaný objekt `ThisDocument` třídy v projekty na úrovni dokumentu ve Wordu.<br />– Ovládací prvky Windows Forms, které můžete použít na dokumenty v projekty aplikace Word.|  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-35"></a>Sestavení v Office rozšíření pro rozhraní .NET Framework 3.5  
 Následující tabulka uvádí sestavení, které jsou součástí rozšíření Office pro rozhraní .NET Framework 3.5. Dokumentaci k obory názvů a třídy v těchto sestavení, najdete v následujícím referenčním oddílu v dokumentaci k sadě Visual Studio 2008: [http://go.microsoft.com/fwlink/?LinkId=160658](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v9.0.dll|Poskytuje následující typy:<br /><br /> -Microsoft.Office.Tools.AddIn základní třída pro doplňků VSTO.<br />-Třídy pro vytváření vlastních nastavení pásu karet a inteligentní značky. **Poznámka:** inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Třídy pro vytváření podokna akcí v přizpůsobeních na úrovni dokumentu a vlastních podoken úloh v doplňků VSTO.|  
|Microsoft.Office.Tools.Excel.v9.0.dll|Poskytuje hostitelských položek a hostitelských ovládacích prvků pro řešení pro aplikaci Excel. Další informace najdete v tématu [automatizace aplikace Excel pomocí rozšířených objekty](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|Poskytuje třídy, které můžete použít k vytvoření vlastního formuláře oblasti v doplňků VSTO pro Outlook.|  
|Microsoft.Office.Tools.Word.v9.0.dll|Poskytuje hostitelských položek a hostitelských ovládacích prvků pro řešení aplikace Word. Další informace najdete v tématu [automatizace aplikace Word pomocí rozšířených objekty](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v9.0.dll|Poskytuje následující typy:<br /><br /> -Microsoft.VisualStudio.Tools.Office.RemoteBindableComponent třídu, která poskytuje funkce vazby dat pro hostitelské ovládací prvky v přizpůsobeních na úrovni dokumentu.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|Poskytuje následující typy:<br /><br /> -Atribut Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute a Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType rozhraní, které můžete použít k mezipaměti datové objekty v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).<br />-Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Poskytuje rozhraní Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction, které můžete implementovat, abyste spusťte další instalační kroky jako poslední krok ClickOnce instalační program pro řešení Office. Další informace najdete v tématu [pokročilé nasazení řešení Office](http://msdn.microsoft.com/en-us/9147b6f6-849f-4cb1-b2c5-e22658d74b02).|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|Poskytuje následující typy:<br /><br /> Třída-Microsoft.VisualStudio.Tools.Applications.ServerDocument, který můžete použít pro programové připojení přizpůsobení sestavení do dokumentů a přístup k data uložená v mezipaměti v dokumentech. Další informace najdete v tématu [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Několik tříd, které představují hierarchii do mezipaměti data v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|Poskytuje následující typy:<br /><br /> -Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry a Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList třídy, které můžete použít k vytvoření uživatele zahrnutí seznam položek můžete udělit vztah důvěryhodnosti pro Office řešení, které cílí na rozhraní .NET Framework 3.5.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Scénáře instalace nástrojů Visual Studio Tools for Office runtime](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  