---
title: Události v projektech pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Sheet1_Startup
- ThisDocument_Shutdown
- ThisDocument_Startup
- application-level add-ins [Office development in Visual Studio], events
- event handlers [Office development in Visual Studio]
- ThisWorkbook_Startup
- Sheet2_Startup
- ThisWorkbook_Shutdown
- document-level customizations [Office development in Visual Studio], events
- Sheet2_Shutdown
- Startup event
- Sheet3_Shutdown
- add-ins [Office development in Visual Studio], events
- Shutdown event
- ThisAddIn_Startup
- Sheet3_Startup
- Startup method [Office development in Visual Studio]
- Shutdown method [Office development in Visual Studio]
- Sheet1_Shutdown
- events [Office development in Visual Studio]
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 10cd0e1740aa53902d266ed0af6820b500a453e9
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448711"
---
# <a name="events-in-office-projects"></a>Události v projektech pro systém Office
  Každá šablona projektu Office automaticky vytvoří několik obslužné rutiny událostí. Obslužné rutiny pro úpravy na úrovni dokumentů se mírně liší od obslužné rutiny události pro doplňky VSTO.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="document-level-projects"></a>Projekty na úrovni dokumentu  
 Visual Studio poskytuje generovaný kód pro nové nebo existující dokumenty nebo listy v přizpůsobeních na úrovni dokumentu. Tento kód vyvolává dvě různé události: **spuštění** a **vypnutí**.  
  
### <a name="startup-event"></a>událost spuštění  
 **Spuštění** událost se vyvolá pro jednotlivé hostitelské položky (dokument, sešitu nebo listu) po dokumentu běží a kód inicializace v sestavení byl spuštěn. Je poslední věcí, kterou ke spuštění v konstruktoru třídy, která běží v váš kód. Další informace o hostitelských položkách najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
 Když vytvoříte projekt na úrovni dokumentu a, Visual Studio vytvoří obslužné rutiny události pro **spuštění** události v souborech generovaného kódu:  
  
-   U projektů Microsoft Office Word, má název obslužné rutiny události `ThisDocument_Startup`.  
  
-   Pro aplikaci Microsoft Office Excel projekty obslužné rutiny událostí mají tyto názvy:  
  
    -   `Sheet1_Startup`  
  
    -   `Sheet2_Startup`  
  
    -   `Sheet3_Startup`  
  
    -   `ThisWorkbook_Startup`  
  
### <a name="shutdown-event"></a>událost vypnutí  
 **Vypnutí** událost se vyvolá pro jednotlivé hostitelské položky (dokument nebo sešit) Pokud je načtený kód do domény aplikace se uvolnit. Je poslední věcí, kterou má být volána ve třídě, jako je zrušeno jeho zavedení.  
  
 Když vytvoříte projekt na úrovni dokumentu a, Visual Studio vytvoří obslužné rutiny události pro **vypnutí** události v souborech generovaného kódu:  
  
-   U projektů Microsoft Office Word, má název obslužné rutiny události `ThisDocument_Shutdown`.  
  
-   Pro aplikaci Microsoft Office Excel projekty obslužné rutiny událostí mají tyto názvy:  
  
    -   `Sheet1_Shutdown`  
  
    -   `Sheet2_Shutdown`  
  
    -   `Sheet3_Shutdown`  
  
    -   `ThisWorkbook_Shutdown`  
  
> [!NOTE]  
>  Neodebírejte ovládací prvky během prostřednictvím kódu programu **vypnutí** obslužné rutiny události dokumentu. Prvky uživatelského rozhraní dokumentu již nejsou k dispozici při **vypnutí** dojde k události. Pokud chcete odebrat ovládacích prvků, než se aplikace zavře, přidejte kód na jinou obslužnou rutinu události, například **BeforeClose** nebo **BeforeSave**.  
  
### <a name="event-handler-method-declarations"></a>Metoda deklarace obslužných rutin událostí  
 Každý deklarace metoda obslužné rutiny události má stejné argumenty do ní předán: *odesílatele* a *e*. V aplikaci Excel *odesílatele* argument odkazuje na list, jako například `Sheet1` nebo `Sheet2`; v aplikaci Word, *odesílatele* argument odkazuje v dokumentu. *e* argument odkazuje na standardní argumenty pro události, které nejsou v tomto případě použít.  
  
 Následující příklad kódu ukazuje výchozí obslužné rutiny událostí v projektech na úrovni dokumentu ve Wordu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#121](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#121)]
 [!code-csharp[Trin_VstcoreWordAutomation#121](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#121)]  
  
 Následující příklad kódu ukazuje výchozí obslužné rutiny událostí v projektech na úrovni dokumentu pro Excel.  
  
> [!NOTE]  
>  Následující příklad kódu ukazuje obslužné rutiny událostí v `Sheet1` třídy. Názvy obslužné rutiny událostí v jiné třídy položky hostitele odpovídají název třídy. Například v `Sheet2` třídy, **spuštění** obslužné rutiny události jmenuje `Sheet2_Startup`. V `ThisWorkbook` třídy, **spuštění** obslužné rutiny události jmenuje `ThisWorkbook_Startup`.  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#83)]
 [!code-vb[Trin_VstcoreExcelAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#83)]  
  
### <a name="order-of-events-in-document-level-excel-projects"></a>Pořadí událostí v aplikaci Excel projekty na úrovni dokumentu  
 **Spuštění** jsou volány obslužné rutiny událostí v projekty aplikace Excel v tomto pořadí:  
  
1.  `ThisWorkbook_Startup`.  
  
2.  `Sheet1_Startup`.  
  
3.  `Sheet2_Startup`.  
  
4.  `Sheet3_Startup`.  
  
5.  Ostatní listy v pořadí.  
  
 **Vypnutí** jsou volány obslužné rutiny událostí v řešení sešitu v tomto pořadí:  
  
1.  `ThisWorkbook_Shutdown`.  
  
2.  `Sheet1_Shutdown`.  
  
3.  `Sheet2_Shutdown`.  
  
4.  `Sheet3_Shutdown`.  
  
5.  Ostatní listy v pořadí.  
  
 Pořadí je určena při kompilaci projektu. Pokud uživatel změní uspořádání listy v době běhu, nezmění pořadí, že události jsou vyvolány při příštím je sešit otevřít nebo uzavřený.  
  
## <a name="vsto-add-in-projects"></a>Projekty doplňku VSTO  
 Visual Studio poskytuje generovaného kódu v doplňcích VSTO. Tento kód vyvolává dvě různé události: <xref:Microsoft.Office.Tools.AddInBase.Startup> a <xref:Microsoft.Office.Tools.AddInBase.Shutdown>.  
  
### <a name="startup-event"></a>událost spuštění  
 <xref:Microsoft.Office.Tools.AddIn.Startup> Událost se vyvolá po načtení doplňku VSTO a kód inicializace v sestavení byl spuštěn. Tato událost se zpracovává souborem `ThisAddIn_Startup` metoda v souboru generovaného kódu.  
  
 Kód na `ThisAddIn_Startup` obslužné rutiny události je první uživatelského kódu, pokud chcete spustit, pokud vaše doplňku VSTO přepsání <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda. V takovém případě `ThisAddIn_Startup` obslužné rutiny události je volána po <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A>.  
  
 Nepřidáte kód `ThisAdd-In_Startup` obslužné rutiny události, pokud kód vyžaduje, aby dokument otevřen. Místo toho přidejte tento kód na událost, která vyvolává aplikaci Office, když uživatel vytvoří nebo otevře dokument. Další informace najdete v tématu [přístup k dokumentu, při spuštění aplikace Office](../vsto/programming-vsto-add-ins.md#AccessingDocuments).  
  
 Další informace o pořadí spuštění doplňků VSTO najdete v tématu [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="shutdown-event"></a>událost vypnutí  
 <xref:Microsoft.Office.Tools.AddInBase.Shutdown> Událost se vyvolá, když je načtený kód do domény aplikace bude odpojen. Tato událost se zpracovává souborem `ThisAddIn_Shutdown` metoda v souboru generovaného kódu. Tuto obslužnou rutinu události je poslední kód uživatele spustit, když doplňku VSTO je odpojen.  
  
#### <a name="shutdown-event-in-outlook-vsto-add-ins"></a>Událost vypnutí v doplňků VSTO pro Outlook  
 <xref:Microsoft.Office.Tools.AddInBase.Shutdown> Událost se vyvolá, pouze v případě, že uživatel zakáže doplňku VSTO pomocí dialogu doplňky modelu COM v aplikaci Outlook. Není vyvolána při ukončení aplikace Outlook. Pokud máte kód, který musí být spuštěn při ukončení aplikace Outlook, je potřeba některou z následujících událostí:  
  
-   <xref:Microsoft.Office.Interop.Outlook.ApplicationEvents_11_Event.Quit> Události <xref:Microsoft.Office.Interop.Outlook.Application> objektu.  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close> Události <xref:Microsoft.Office.Interop.Outlook.Explorer> objektu.  
  
> [!NOTE]  
>  Můžete vynutit Outlook zvýšit <xref:Microsoft.Office.Tools.AddInBase.Shutdown> událost v případě, že ho ukončí pomocí úpravy registru. Ale pokud správce vrátí toto nastavení, žádný kód přidat do `ThisAddIn_Shutdown` metoda už běží při ukončení aplikace Outlook. Další informace najdete v tématu [vypnutí změny pro aplikaci Outlook 2010](http://go.microsoft.com/fwlink/?LinkID=184614).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Úpravy na úrovni dokumentů programu](../vsto/programming-document-level-customizations.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)  
  
  