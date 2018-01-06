---
title: "Postupy: naplnění listů daty z databáze | Microsoft Docs"
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
- worksheets [Office development in Visual Studio], populating
- databases [Office development in Visual Studio], populating worksheets
- data [Office development in Visual Studio], adding to worksheets
ms.assetid: e9e37cf1-53ca-45d0-8409-5428be7f96c5
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6efeccfdaa6b3377869fb20f9c66613960529daf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-populate-worksheets-with-data-from-a-database"></a>Postupy: Naplnění listů daty z databáze
  Stejným způsobem, že vám přístup k datům ve Windows Forms projekty můžou k datům ve projekty na úrovni dokumentu Office. Použít stejnou nástroje a kódu přenést data do vašeho řešení a ovládací prvky Windows Forms můžete použít i k zobrazení dat. Kromě toho můžete využít názvem hostitelské ovládací prvky, které jsou nativní objekty v aplikaci Microsoft Office Excel vylepšily se události a možnosti datové vazby ovládacích prvků. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Následující příklad ukazuje, jak přidat ovládací prvky vázané na data v projekty na úrovni dokumentu pomocí návrháře. Příklad, jak přidat ovládací prvky vázané na data v projektech na úrovni aplikace za běhu, naleznete v části [návod: komplexní datové vazby v VSTO doplňku projektu](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: přenosu dat do sešit aplikace Excel?](http://go.microsoft.com/fwlink/?LinkID=130277), a [jak provést I: využívat Data databáze v aplikaci Excel?](http://go.microsoft.com/fwlink/?LinkID=130287).  
  
## <a name="adding-a-data-bound-control-to-a-worksheet-at-design-time"></a>Přidání ovládacího prvku vázané na Data na list v době návrhu  
  
#### <a name="to-populate-a-worksheet-with-data-from-a-database"></a>K naplnění listů daty z databáze  
  
1.  Otevření projektu na úrovni dokumentu aplikace Excel v sadě Visual Studio, s otevřete sešit v návrháři.  
  
2.  Otevřete **zdroje dat** okno a vytvořte zdroj dat pro váš projekt. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
3.  Přetáhněte pole nebo chcete z tabulky **zdroje dat** okna do listu.  
  
 Jeden z těchto ovládacích je vytvořen v listu:  
  
-   Pokud přetáhněte pole, <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je vytvořen v listu. Další informace najdete v tématu [NamedRange – ovládací prvek](../vsto/namedrange-control.md).  
  
-   Pokud přetáhnete tabulku, <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek je vytvořen v listu. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).  
  
 Můžete přidat jinou ovládacího prvku tak, že vyberete v tabulce nebo pole v **zdroje dat** okna a pak vyberete různé ovládací prvek z rozevíracího seznamu.  
  
## <a name="objects-in-the-project"></a>Objekty v projektu  
 Kromě ovládacího prvku jsou automaticky přidány následující data související s objekty do projektu:  
  
-   Typové datové sady, který zapouzdřuje datových tabulek, které jste připojeni k v databázi. Další informace najdete v tématu [datové sady nástrojů v sadě Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
-   A <xref:System.Windows.Forms.BindingSource> ovládacího prvku která se připojuje k typové datové sady. Další informace najdete v tématu [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview).  
  
-   TableAdapter, která se připojuje k databázi typové datové sady. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
-   TableAdapterManager, který se používá ke koordinaci adaptéry tabulek v datové sadě umožňující hierarchické aktualizace. Další informace najdete v tématu [hierarchické aktualizace](../data-tools/hierarchical-update.md) a [TableAdapterManager odkaz](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference).  
  
 Při spuštění projektu zobrazí ovládací prvek ve zdroji dat na první záznam. Můžete použít <xref:System.Windows.Forms.BindingSource> umožňuje uživatelům procházet záznamů.  
  
#### <a name="to-scroll-through-the-records"></a>Chcete-li procházet záznamů  
  
-   Použití <xref:System.Windows.Forms.BindingSource> metody, jako <xref:System.Windows.Forms.BindingSource.MoveNext%2A> a <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>.  
  
 Informace o tom, jak odesílání aktualizací na typové datové sady a databáze najdete v tématu [postup: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources)   
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)   
 [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Jak I: přenosu dat do sešitu aplikace Excel](http://go.microsoft.com/fwlink/?LinkID=130277)   
 [Způsob, jakým se I: využívají Data databáze v aplikaci Excel](http://go.microsoft.com/fwlink/?LinkID=130287)  
  
  