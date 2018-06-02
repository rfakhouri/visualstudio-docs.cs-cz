---
title: Úpravy na úrovni dokumentů programu
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Sheet3
- thisWorkbook
- thisDocument
- Sheet1
- Sheet2
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ThisDocument class
- Sheet3 class
- ThisWorkbook class
- writing code for Office solutions
- programming [Office development in Visual Studio], document-level customizations
- Sheet1 class
- Office applications [Office development in Visual Studio], document-level customizations
- Sheet2 class
- document-level customizations [Office development in Visual Studio], programming
- application development [Office development in Visual Studio], document-level customizations
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 512952a27e2b1c22df256e36f8cbea59f04a3295
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692828"
---
# <a name="program-document-level-customizations"></a>Úpravy na úrovni dokumentů programu
  Když rozšíříte aplikace Microsoft Office Word nebo Microsoft Office Excel pomocí přizpůsobení na úrovni dokumentu, můžete provádět následující úlohy:  
  
-   Automatizace aplikace pomocí jeho objektového modelu.  
  
-   Přidání ovládacích prvků na plochu dokumentu.  
  
-   Volání jazyka Visual Basic pro aplikace (VBA) kód v dokumentu ze sestavení vlastní nastavení.  
  
-   Volání kódu v sestavení přizpůsobení z jazyka VBA.  
  
-   Spravujte některé aspekty dokumentu, když je na serveru, který nemá nainstalovanou sadu Microsoft Office.  
  
-   Přizpůsobení uživatelského rozhraní (UI) aplikace.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Některé aspekty psaní kódu v projekty na úrovni dokumentu se liší od ostatních typů projektů v sadě Visual Studio. Řadu tyto rozdíly jsou příčinou způsob Office – objektové modely jsou umístěny do spravovaného kódu. Další informace najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
 Obecné informace o přizpůsobení na úrovni dokumentu a dalších typů řešení, která můžete vytvořit pomocí nástroje pro vývoj pro Office v sadě Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="use-the-generated-classes-in-document-level-projects"></a>Použít generované třídy v projekty na úrovni dokumentu  
 Když vytvoříte projekt na úrovni dokumentu a, Visual Studio automaticky vygeneruje třídu v projektu, který můžete zahájit zápis kódu. Visual Studio vytváří různé třídy pro Word a Excel:  
  
-   V projektech na úrovni dokumentu ve Wordu, se nazývá třída `ThisDocument` ve výchozím nastavení.  
  
-   Projekty na úrovni dokumentu pro Excel mít více generované třídy: jeden pro vlastní sešit a jeden pro každou listu. Ve výchozím nastavení mají tyto třídy tyto názvy:  
  
    -   `ThisWorkbook`  
  
    -   `Sheet1`  
  
    -   `Sheet2`  
  
    -   `Sheet3`  
  
 Generovaná třída zahrnuje obslužné rutiny, které jsou volána, když je dokument otevřít nebo uzavřený. Ke spuštění kódu při otevření dokumentu, přidejte kód, který `Startup` obslužné rutiny události. Pokud chcete spustit kód bezprostředně před zavření dokumentu, přidejte kód, který `Shutdown` obslužné rutiny události. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
### <a name="understand-the-design-of-the-generated-classes"></a>Pochopení návrh vygenerované třídy  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], hostitelská položka typy, které do [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] jsou rozhraní, takže generované třídy nelze odvodit z nich jejich provádění. Místo toho generované třídy odvozeny většinu jejich členové ze základní třídy, které následující:  
  
-   `ThisDocument`: odvozuje od <xref:Microsoft.Office.Tools.Word.DocumentBase>.  
  
-   `ThisWorkbook`: odvozuje od <xref:Microsoft.Office.Tools.Excel.WorkbookBase>.  
  
-   `Sheet` *n*: odvozuje od <xref:Microsoft.Office.Tools.Excel.WorksheetBase>.  
  
 Tyto základní třídy přesměrovat všechna volání do jejich členové interních implementací rozhraní odpovídající položky hostitele v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Například, pokud zavoláte <xref:Microsoft.Office.Tools.Word.DocumentBase.Protect%2A> metodu `ThisDocument` třídy, <xref:Microsoft.Office.Tools.Word.DocumentBase> třída přesměruje toto volání na interní implementaci <xref:Microsoft.Office.Tools.Word.Document> rozhraní v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="access-the-object-model-of-the-host-application"></a>Přístup k modelu objektu hostitele aplikace  
 Pro přístup k modelu objektu hostitelské aplikace, použijte členy generované třídy ve vašem projektu. Každá z těchto tříd odpovídá objektu v modelu objektů aplikace Excel nebo Word a obsahují většinu stejné vlastnosti, metod a události. Například `ThisDocument` třídy v projektech na úrovni dokumentu pro Word poskytuje nejvíc členy stejné, jako <xref:Microsoft.Office.Interop.Word.Document> objekt ve model objektů aplikace Word.  
  
 Následující příklad kódu ukazuje, jak používat model objektů aplikace Word uložte dokument, který je součástí přizpůsobení na úrovni dokumentu ve Wordu. Tento příklad je určený pro spouštění z `ThisDocument` třídy.  
  
```vb  
Me.Save()  
```  
  
```csharp  
this.Save();  
```  
  
 Uděláte to samé z mimo `ThisDocument` třídy, použijte `Globals` objektu pro přístup k `ThisDocument` třídy. Například můžete přidat tento kód do souboru kódu podokna akce Pokud chcete zahrnout **Uložit** tlačítko v podokně Akce uživatelského rozhraní.  
  
```vb  
Globals.ThisDocument.Save()  
```  
  
```csharp  
Globals.ThisDocument.Save();  
```  
  
 Protože `ThisDocument` třída získá většinu svých členů z <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka `Save` metoda, která je volána v tento kód je ve skutečnosti <xref:Microsoft.Office.Tools.Word.Document.Save%2A> metodu <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka. Tato metoda odpovídá <xref:Microsoft.Office.Interop.Word._Document.Save%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt ve model objektů aplikace Word.  
  
 Další informace o používání objektové modely aplikace Word a Excel najdete v tématu [přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md) a [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).  
  
 Další informace o `Globals` objektu, najdete v části [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
## <a name="add-controls-to-documents"></a>Přidání ovládacích prvků do dokumentů  
 Pro přizpůsobení uživatelského rozhraní dokumentu, můžete přidat ovládací prvky Windows Forms nebo *hostování ovládacích prvků* na plochu dokumentu. Kombinování různé sady ovládacích prvků a psaní kódu, že ovládací prvky můžete vázat na data, shromáždit informace od uživatele a reagovat na akce uživatele.  
  
 Hostitelské ovládací prvky jsou třídy, které rozšiřují některé objekty v modelu objektů aplikace Word a Excel. Například <xref:Microsoft.Office.Tools.Excel.ListObject> hostitelského ovládacího prvku poskytuje všechny funkce <xref:Microsoft.Office.Interop.Excel.ListObject> v aplikaci Excel. Ale <xref:Microsoft.Office.Tools.Excel.ListObject> hostitelského ovládacího prvku má také další události a možnosti data vazby.  
  
 Další informace najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md) a [Windows forms – ovládací prvky na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
## <a name="combine-vba-and-document-level-customizations"></a>Kombinování VBA pro vytváření a úpravy na úrovni dokumentů  
 VBA kód můžete použít v dokumentu, který je součástí přizpůsobení na úrovni dokumentu. VBA kód můžete volat v dokumentu z sestavení vlastní nastavení a můžete také nakonfigurovat projektu povolit VBA kód v dokumentu pro volání kódu v sestavení vlastní nastavení.  
  
 Další informace najdete v tématu [kombinovat VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
## <a name="manage-documents-on-a-server"></a>Správa dokumentů na serveru  
 Můžete spravovat několik různých aspektů úpravy na úrovni dokumentů na serveru, který nemá aplikace Microsoft Office Word nebo nainstalována aplikace Microsoft Office Excel. Například můžete používat a upravovat data v datové mezipaměti dokumentu. Můžete také spravovat přizpůsobení sestavení, které je přidružené k dokumentu. Například můžete programově odebrat sestavení z dokumentu tak, aby dokument už běží váš kód nebo sestavení prostřednictvím kódu programu můžete připojit k dokumentu.  
  
 Další informace najdete v tématu [správě dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).  
  
## <a name="customize-the-user-interface-of-microsoft-office-applications"></a>Přizpůsobení uživatelského rozhraní aplikace Microsoft Office  
 Pomocí přizpůsobení na úrovni dokumentu, můžete přizpůsobit uživatelského rozhraní aplikace Word a Excel následujícími způsoby:  
  
-   Přidání hostitelské ovládací prvky nebo ovládací prvky Windows Forms do prostor dokumentu.  
  
     Další informace najdete v tématu [automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md), [automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md), a [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
-   Přidání podokna akcí v dokumentu.  
  
     Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
-   Přidáte vlastní karty na pásu karet.  
  
     Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
-   Přidáte vlastní skupiny do předdefinované karty na pásu karet.  
  
     Další informace najdete v tématu [postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md).  
  
 Další informace o přizpůsobení uživatelského rozhraní aplikace Microsoft Office aplikací najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="get-extended-objects-from-native-office-objects-in-document-level-customizations"></a>Získání rozšířených objektů z nativních Office objektů v přizpůsobeních na úrovni dokumentu  
 Mnoho obslužné rutiny události pro události Office přijímat objekt nativní Office, který představuje sešitu, listu nebo dokument, který vyvolá událost. V některých případech můžete chtít spouštět nějaký kód pouze v případě, že sešitu nebo dokumentu v přizpůsobení na úrovni dokumentu vyvolá událost. Například v přizpůsobení na úrovni dokumentu pro Excel, můžete chtít spouštět nějaký kód, když uživatel aktivuje mezi listy v vlastní sešit, ale ne v případě, že uživatel aktivuje list některé sešitu, který se stane být otevřený ve stejnou dobu.  
  
 Až budete mít objekt nativní Office, můžete zkontrolovat, zda tento objekt se rozšířily do *hostitelská položka* nebo *hostování ovládacího prvku* v přizpůsobení na úrovni dokumentu. Hostitelských položek a hostitelských ovládacích prvků jsou typy poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] přidá funkce pro objekty, které nativně existovat v objektové modely Word či Excel (nazývá *nativních objektů Office*). Dále souhrnně nazývané hostitelských položek a hostitelských ovládacích prvků se také označují jako *rozšířených objektů*. Další informace o hostitelských položek a hostitelských ovládacích prvků najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="understand-the-getvstoobject-and-hasvstoobject-methods"></a>Porozumění metodám getvstoobject – a hasvstoobject –  
 Chcete-li otestovat objekt nativní Office, použijte `HasVstoObject` a `GetVstoObject` metody ve vašem projektu:  
  
-   Použití `HasVstoObject` metoda, pokud chcete určit, zda má objekt nativní Office rozšířené objekt ve vašem vlastním přizpůsobení. Tato metoda vrátí hodnotu **true** pokud nativní objekt Office má objekt rozšířené, a **false** jinak.  
  
-   Použití `GetVstoObject` metoda, pokud chcete získat delší objektu pro objekt nativní Office. Tato metoda vrátí hodnotu <xref:Microsoft.Office.Tools.Excel.ListObject>, <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>, nebo <xref:Microsoft.Office.Tools.Word.Document> objektu, pokud se zadaný objekt nativní Office jeden má. V opačném `GetVstoObject` vrátí **null**. Například `GetVstoObject` metoda vrátí <xref:Microsoft.Office.Tools.Word.Document> Pokud zadaný <xref:Microsoft.Office.Interop.Word.Document> je základní objekt pro dokument ve vašem projektu dokumentu aplikace Word.  
  
 V projekty na úrovni dokumentu, nelze použít `GetVstoObject` metodu pro vytvoření nové <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>, nebo <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka za běhu. Tuto metodu můžete použít pouze pro přístup k existující položky hostitele, které se generují ve vašem projektu v době návrhu. Pokud chcete vytvořit nové hostitele položky v době běhu, je třeba vytvořit projektu doplňku VSTO. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md) a [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="use-the-getvstoobject-and-hasvstoobject-methods"></a>Použít getvstoobject – a hasvstoobject – metody  
 K volání `HasVstoObject` a `GetVstoObject` metoda, použijte `Globals.Factory.GetVstoObject` nebo `Globals.Factory.HasVstoObject` metoda a předejte jí objekt nativní Word či Excel (například <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Worksheet>), kterou chcete otestovat.  
  
## <a name="see-also"></a>Viz také:  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Správa dokumentů na serveru s použitím třídy ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
  