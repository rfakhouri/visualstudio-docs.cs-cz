---
title: Sestavení sady Visual Studio Tools for Office runtime
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, assemblies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8ff32d472d0e2005b22acb8d751e03c6aa3f61ef
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="assemblies-in-the-visual-studio-tools-for-office-runtime"></a>Sestavení sady Visual Studio Tools for Office runtime
  Když vytvoříte projekt Office, Visual Studio automaticky přidá reference na [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] sestavení, které se používají pro typ projektu a cílové rozhraní .NET Framework projektu. V rozšíření Office pro rozhraní .NET Framework 3.5, existují různé sestavení [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], a [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Další informace o rozšířeních Office, najdete v části [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-4-and-the-includenetv45vstoincludesnet-v45-mdmd"></a>Sestavení v Office rozšíření pro rozhraní .NET Framework 4 a [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 Následující tabulka uvádí sestavení, které jsou součástí Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Dokumentaci o obory názvů a typy v těchto sestavení najdete v tématu [řízené reference &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/managed-reference-office-development-in-visual-studio.md).  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.dll|Poskytuje následující typy:<br /><br /> -Typy pro vytváření vlastních nastavení pásu karet a inteligentní značky. **Poznámka:** inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Typy pro vytvoření podokna akcí v přizpůsobeních na úrovni dokumentu a vlastních podoken úloh v doplňků VSTO.|  
|Microsoft.Office.Tools.Excel.dll|Poskytuje rozhraní, které představují hostitelských položek a hostitelských ovládacích prvků pro projekty aplikace Excel a podpůrné typy. Další informace najdete v tématu [automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.dll|Obsahuje typy, které můžete použít k vytvoření vlastního formuláře oblasti v doplňků VSTO pro Outlook.|  
|Microsoft.Office.Tools.Word.dll|Poskytuje rozhraní, které představují hostitelských položek a hostitelských ovládacích prvků pro projekty aplikace Word a podpůrné typy. Další informace najdete v tématu [automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v4.0.Framework.dll|Poskytuje následující typy:<br /><br /> -Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Atributy, které můžete použít při vytváření aplikace Outlook formuláři oblasti.|  
|Microsoft.Office.Tools.dll|Obsahuje typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut a <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> rozhraní, které můžete použít k mezipaměti datové objekty v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).<br />-Na <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> rozhraní, které můžete implementovat, abyste spusťte další instalační kroky jako poslední krok ClickOnce instalační program pro řešení Office. Další informace najdete v tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).<br />-Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy, které můžete použít k přizpůsobení sestavení připojení k dokumentům a přístup k data uložená v mezipaměti v dokumentech. Další informace najdete v tématu [správě dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Několik tříd, které představují hierarchii do mezipaměti data v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|  
  
 Projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] také odkazují následující sestavení. Tyto sestavení nejsou součástí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] redistributable. Místo toho jsou závislé sestavení, které musí být nasazené s vaším řešením. Ve výchozím nastavení, se kopírují do výstupní složky sestavení projektu ( **místní kopie** vlastnost pro tyto sestavení jsou nastavena na **True**). Pokud nasadíte projektu s použitím technologie ClickOnce, jsou tyto sestavení součástí vygenerovaný balíček.  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|Poskytuje základní třídy pro generovaný objekt `ThisAddIn` třídy v projekty doplňku VSTO a generovaná třída pásu karet ve všech projektech.|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|Poskytuje následující typy:<br /><br /> -Základní třídy pro generovaný objekt `ThisWorkbook` a `Sheet` třídy v úrovni dokumentu projekty pro aplikaci Excel.<br />– Ovládací prvky Windows Forms, které můžete použít na listech v projekty aplikace Excel.|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Poskytuje základní třídy pro generovaný objekt `ThisAddIn` a třídy oblastí formulářů v projektech Outlook.|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|Poskytuje následující typy:<br /><br /> -Základní třídy pro generovaný objekt `ThisDocument` třídy v projekty na úrovni dokumentu ve Wordu.<br />– Ovládací prvky Windows Forms, které můžete použít na dokumenty v projekty aplikace Word.|  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-35"></a>Sestavení v Office rozšíření pro rozhraní .NET Framework 3.5  
 Následující tabulka uvádí sestavení, které jsou součástí rozšíření Office pro rozhraní .NET Framework 3.5. Dokumentaci k obory názvů a třídy v těchto sestavení, najdete v následujícím referenčním oddílu v dokumentaci k sadě Visual Studio 2008: [ http://go.microsoft.com/fwlink/?LinkId=160658 ](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
|Název sestavení|Popis|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v9.0.dll|Poskytuje následující typy:<br /><br /> -Microsoft.Office.Tools.AddIn základní třída pro doplňků VSTO.<br />-Třídy pro vytváření vlastních nastavení pásu karet a inteligentní značky. **Poznámka:** inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Třídy pro vytváření podokna akcí v přizpůsobeních na úrovni dokumentu a vlastních podoken úloh v doplňků VSTO.|  
|Microsoft.Office.Tools.Excel.v9.0.dll|Poskytuje hostitelských položek a hostitelských ovládacích prvků pro řešení pro aplikaci Excel. Další informace najdete v tématu [automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|Poskytuje třídy, které můžete použít k vytvoření vlastního formuláře oblasti v doplňků VSTO pro Outlook.|  
|Microsoft.Office.Tools.Word.v9.0.dll|Poskytuje hostitelských položek a hostitelských ovládacích prvků pro řešení aplikace Word. Další informace najdete v tématu [automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v9.0.dll|Poskytuje následující typy:<br /><br /> -Na [RemoteBindableComponent](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb546360(v=vs.90)) třídy, která poskytuje funkce vazby dat pro hostitelské ovládací prvky v úrovni dokumentu přizpůsobení.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut a <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> rozhraní, které můžete použít k mezipaměti datové objekty v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).<br />-Výjimky, které mohou být vyvolány sady Visual Studio Tools for Office runtime.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Poskytuje <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> rozhraní, které můžete implementovat, abyste spusťte další instalační kroky jako poslední krok ClickOnce instalační program pro řešení Office. Další informace najdete v tématu [nasazení řešení Advanced Office](http://msdn.microsoft.com/en-us/9147b6f6-849f-4cb1-b2c5-e22658d74b02).|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|Poskytuje následující typy:<br /><br /> -Na <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy, které můžete použít pro programové připojení přizpůsobení sestavení do dokumentů a přístup k data uložená v mezipaměti v dokumentech. Další informace najdete v tématu [správě dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Několik tříd, které představují hierarchii do mezipaměti data v přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|Poskytuje následující typy:<br /><br /> -Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry a Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList třídy, které můžete použít k vytvoření uživatele zahrnutí seznam položek můžete udělit vztah důvěryhodnosti pro Office řešení, které cílí na rozhraní .NET Framework 3.5.<br />-Jiné typy, které jsou součástí Visual Studio Tools for Office runtime infrastrukturu a není určena pro použití přímo z vašeho kódu.|  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Visual Studio Tools for Office runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  