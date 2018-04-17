---
title: Programování doplňků VSTO | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.Addin
- VST.ProjectItem.AddinProject
- thisAddIn
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ICustomTaskPaneConsumer interface
- add-ins [Office development in Visual Studio], programming
- IRibbonExtensibility interface
- UI customizing [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], application-level add-ins
- programming [Office development in Visual Studio], application-level add-ins
- ThisAddIn class
- user interfaces [Office development in Visual Studio], customizing
- writing code for Office solutions
- host items [Office development in Visual Studio], AddIn
- application development [Office development in Visual Studio], application-level add-ins
- add-ins [Office development in Visual Studio], ThisAddIn class
- application-level add-ins [Office development in Visual Studio], ThisAddIn class
- FormRegionStartup interface
- ThisAddIn_Startup
- application-level add-ins [Office development in Visual Studio], programming
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 192b366b4d41fed0baf0cca4af8e57fa00dc249a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="programming-vsto-add-ins"></a>Programování doplňků VSTO
  Když rozšíříte tak, že vytvoříte doplňku VSTO aplikace Microsoft Office, můžete napsat kód přímo na `ThisAddIn` třídy ve vašem projektu. Tato třída slouží k provádění úloh, jako je přístup k modelu objektu hostitelské aplikace Microsoft Office, přizpůsobení uživatelského rozhraní (UI) aplikace a vystavení objektů v doplňku VSTO pro jiné řešení pro Office.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Některé aspekty psaní kódu v doplňku VSTO projekty se liší od ostatních typů projektů v sadě Visual Studio. Řadu tyto rozdíly jsou příčinou způsob Office – objektové modely jsou umístěny do spravovaného kódu. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
 Obecné informace o doplňků VSTO a dalších typů řešení, která můžete vytvořit pomocí nástroje pro vývoj pro Office v sadě Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="using-the-thisaddin-class"></a>Pomocí ThisAddIn – třída  
 Psaní kódu doplňku VSTO v můžete spustit `ThisAddIn` třídy. Visual Studio automaticky generuje této třídy v ThisAddIn.vb (v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) nebo ThisAddIn.cs (v jazyku C#) souboru kódu v projektu doplňku VSTO. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Pro vás automaticky vytvoří tato třída při načtení aplikace Microsoft Office vaší doplňku VSTO.  
  
 Existují dvě obslužné rutiny výchozí událostí v `ThisAddIn` třídy. Ke spuštění kódu při doplňku VSTO je načtena, přidejte kód, který `ThisAddIn_Startup` obslužné rutiny události. Pokud chcete spustit kód bezprostředně před doplňku VSTO je odpojen, přidejte kód, který `ThisAddIn_Shutdown` obslužné rutiny události. Další informace o těchto obslužných rutinách událostí najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
> [!NOTE]  
>  V aplikaci Outlook, ve výchozím nastavení `ThisAddIn_Shutdown` obslužné rutiny události není volána vždy, když doplňku VSTO je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
### <a name="accessing-the-object-model-of-the-host-application"></a>Přístup k modelu objektu hostitele aplikace  
 Pro přístup k modelu objektu hostitelské aplikace, použijte `Application` pole z `ThisAddIn` třídy. Toto pole vrátí objekt, který představuje aktuální instanci hostitelskou aplikaci. Následující tabulka uvádí typ vrácené hodnoty pro `Application` pole v každém projektu doplňku VSTO.  
  
|hostitelskou aplikaci|Vrátí typ hodnoty|  
|----------------------|-----------------------|  
|Aplikace Microsoft Office Excel|<xref:Microsoft.Office.Interop.Excel.Application>|  
|Aplikace Microsoft Office InfoPath|<xref:Microsoft.Office.Interop.InfoPath.Application>|  
|Aplikace Microsoft Office Outlook|<xref:Microsoft.Office.Interop.Outlook.Application>|  
|Aplikace Microsoft Office PowerPoint|<xref:Microsoft.Office.Interop.PowerPoint.Application>|  
|Aplikace Microsoft Office Project|Microsoft.Office.Interop.MSProject.Application|  
|Aplikace Microsoft Office Visio|Microsoft.Office.Interop.Visio.Application|  
|Aplikace Microsoft Office Word|<xref:Microsoft.Office.Interop.Word.Application>|  
  
 Následující příklad kódu ukazuje, jak používat `Application` pole, které chcete vytvořit nový sešit v doplňku VSTO pro aplikaci Microsoft Office Excel. Tento příklad je určený pro spouštění z `ThisAddIn` třídy.  
  
```vb  
Dim newWorkbook As Excel.Workbook = Me.Application.Workbooks.Add()  
```  
  
```csharp  
Excel.Workbook newWorkbook = this.Application.Workbooks.Add(System.Type.Missing);  
```  
  
 Uděláte to samé z mimo `ThisAddIn` třídy, použijte `Globals` objektu pro přístup k `ThisAddIn` třídy. Další informace o `Globals` objektu, najdete v části [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
```vb  
Dim newWorkbook As Excel.Workbook = Globals.ThisAddIn.Application.Workbooks.Add()  
```  
  
```csharp  
Excel.Workbook newWorkbook = Globals.ThisAddIn.Application.Workbooks.Add(System.Type.Missing);  
```  
  
 Další informace o objektu modely konkrétní aplikace Microsoft Office najdete v následujících tématech:  
  
-   [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)  
  
-   [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)  
  
-   [InfoPath – řešení](../vsto/infopath-solutions.md)  
  
-   [Řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md)  
  
-   [Projektová řešení](../vsto/project-solutions.md)  
  
-   [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)  
  
###  <a name="AccessingDocuments"></a> Přístup k dokumentu, při spuštění aplikace Office  
 Ne všechny [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] aplikace automaticky otevře při spuštění je a žádný z dokumentu [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] aplikace otevřete dokument, při jejich spuštění. Proto nepřidáte kód `ThisAdd-In_Startup` obslužné rutiny události, pokud kód vyžaduje, aby dokument otevřen. Místo toho přidejte tento kód na událost, která vyvolává aplikaci Office, když uživatel vytvoří nebo otevře dokument. Tímto způsobem může zaručit, že dokument je otevřen před kódu provádí operace na něm.  
  
 Následující příklad kódu funguje s dokumentem v aplikaci Word jenom v případě, že uživatel vytvoří dokument nebo otevře existující dokument.  
  
 [!code-csharp[Trin_WordAddIn_Menus#3](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#3)]
 [!code-vb[Trin_WordAddIn_Menus#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#3)]  
  
### <a name="thisaddin-members-to-use-for-other-tasks"></a>ThisAddIn členy na použití pro jiné úlohy  
 Následující tabulka popisuje dalších běžných úloh a ukazuje, kteří členové `ThisAddIn` třídu můžete použít k provádění úloh.  
  
|Úloha|Člen používat|  
|----------|-------------------|  
|Spuštění kódu k chybě při inicializaci doplňku VSTO při načítání doplňku VSTO.|Přidejte kód, který `ThisAddIn_Startup` metoda. Toto je výchozí obslužnou rutinu <xref:Microsoft.Office.Tools.AddInBase.Startup> událostí. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).|  
|Spusťte kód na vyčištění prostředky využívané třídou doplňku VSTO před doplňku VSTO je odpojen.|Přidejte kód, který `ThisAddIn_Shutdown` metoda. Toto je výchozí obslužnou rutinu <xref:Microsoft.Office.Tools.AddInBase.Shutdown> událostí. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md). **Poznámka:** v aplikaci Outlook, ve výchozím nastavení `ThisAddIn_Startup` obslužné rutiny události není volána vždy, když doplňku VSTO je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).|  
|Zobrazení vlastního podokna úloh.|Použití `CustomTaskPanes` pole. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).|  
|Vystavení objektů v doplňku VSTO pro jiné řešení pro Microsoft Office.|Přepsání <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda. Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).|  
|Implementace rozhraní rozšiřitelnosti přizpůsobte funkce v systému Microsoft Office.|Přepsání <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda vrátit instanci třídy, která implementuje rozhraní. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní funkce pomocí pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md). **Poznámka:** k přizpůsobení pásu karet uživatelského rozhraní, můžete také přepsat <xref:Microsoft.Office.Tools.AddInBase.CreateRibbonExtensibilityObject%2A> metoda.|  
  
### <a name="understanding-the-design-of-the-thisaddin-class"></a>Principy návrhu ThisAddIn – třída  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], <xref:Microsoft.Office.Tools.AddIn> je rozhraní. `ThisAddIn` Třída odvozená z <xref:Microsoft.Office.Tools.AddInBase> třídy. Tato základní třída přesměruje všechny její členy volání na interní implementace <xref:Microsoft.Office.Tools.AddIn> rozhraní v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 Projekty doplňku VSTO pro Outlook `ThisAddIn` třída odvozena od třídy Microsoft.Office.Tools.Outlook.OutlookAddIn v projektech cílených pro rozhraní .NET Framework 3.5 a z <xref:Microsoft.Office.Tools.Outlook.OutlookAddInBase> v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Tyto základní třídy poskytují některé další funkce pro podporu oblasti formuláře. Další informace o oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
## <a name="customizing-the-user-interface-of-microsoft-office-applications"></a>Přizpůsobení uživatelského rozhraní aplikace Microsoft Office  
 Prostřednictvím kódu programu můžete přizpůsobit aplikace uživatelského rozhraní aplikace Microsoft Office pomocí doplňku VSTO. Můžete například přizpůsobení pásu karet, zobrazí vlastního podokna úloh nebo vytvořit vlastní formulář oblasti v aplikaci Outlook. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
 Visual Studio poskytuje návrháři a třídy, které můžete použít k vytvoření vlastních podoken úloh, vlastních nastavení pásu karet a oblastí formulářů aplikace Outlook. Tyto programy Designer a třídy pomáhají zjednodušit proces přizpůsobení těchto funkcí. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md), [Návrhář pásu karet](../vsto/ribbon-designer.md), a [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
 Pokud chcete přizpůsobit jedna z těchto funkcí způsobem, který nepodporuje třídy a návrhářů, můžete také přizpůsobit tyto funkce implementací *rozšiřitelnost rozhraní* v doplňku VSTO. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní funkce pomocí pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md).  
  
 Kromě toho můžete upravit dokumenty uživatelského rozhraní aplikace Word a sešitů aplikace Excel pomocí generování hostitelské položky, které rozšiřují chování dokumentů a sešitů. Umožňuje přidání spravovaných ovládacích prvků do dokumentů a listů. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="calling-code-in-vsto-add-ins-from-other-solutions"></a>Volání kódu v doplňcích VSTO z jiných řešení  
 Objekty můžou zpřístupnit v doplňku VSTO do jiných řešení, včetně jiných řešení pro Office. To je užitečné, pokud vaše doplňku VSTO poskytuje službu, která chcete povolit jiné řešení použít. Například pokud máte doplňku VSTO pro aplikaci Microsoft Office Excel, který provádí výpočtů finančních dat z webové služby, jiná řešení můžete provést tyto výpočty volání do doplněk aplikace Excel VSTO za běhu.  
  
 Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Návod: Volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)   
 [Přizpůsobení funkcí uživatelského rozhraní pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
  