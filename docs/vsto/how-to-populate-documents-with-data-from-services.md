---
title: "Postupy: naplnění dokumentů daty ze služeb | Microsoft Docs"
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
- documents [Office development in Visual Studio], populating with data
- Web services [Office development in Visual Studio], populating documents
- data [Office development in Visual Studio], adding to documents
ms.assetid: 4c42653c-627f-445e-9024-8482eaf5562e
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5cdcfc080251d62bf0f7dbede2016b4821383c5a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-populate-documents-with-data-from-services"></a>Postupy: Naplnění dokumentů daty ze služeb
  Přístup k datům funguje stejným způsobem jako v projekty na úrovni dokumentu pro Microsoft Office jako v systému Windows Forms projekty. Použít stejnou nástroje a kódu přenést data do vašeho řešení a ovládací prvky Windows Forms můžete použít i k zobrazení dat. Kromě toho můžete využít názvem hostitelské ovládací prvky, které jsou nativní objekty v aplikaci Microsoft Office Excel a Microsoft Office Word vylepšily se události a možnosti data vazba ovládacích prvků. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Následující příklad ukazuje, jak přidat ovládací prvky vázané na data do dokumentů v době návrhu. Příklad, jak přidat ovládací prvky vázané na data v doplňcích VSTO za běhu, naleznete v části [návod: vytvoření vazby na Data ze služby v VSTO doplňku projektu](../vsto/walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [provést I: interakci s webovými službami z aplikace Microsoft Excel?](http://go.microsoft.com/fwlink/?LinkID=130284).  
  
### <a name="to-populate-a-document-level-project-with-data-from-a-web-service"></a>K naplnění projekt na úrovni dokumentu a s daty z webové služby  
  
1.  Otevřete **zdroje dat** okno a vytvořte zdroj dat služby pro váš projekt. Další informace najdete v tématu [přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources).  
  
2.  Přetáhněte tabulku nebo pole, které chcete z **zdroje dat** okna dokumentu.  
  
     Vytvoření ovládacího prvku v dokumentu, <xref:System.Windows.Forms.BindingSource> se vytvoří, je vázán k třídu objektu ve vašem projektu a se generují třídy pro službu.  
  
3.  V kódu vytvoření instance třídy webové služby, která je připojena k v kroku 1.  
  
4.  Pokud existují vlastnosti, které jsou požadovány pro komunikaci s webovou službu, vytvořte instance tyto vlastnosti.  
  
5.  Vytvoření a odeslání požadavku na data pomocí metody vystavené webové služby a všechny instance vlastnost, že kterou jste vytvořili v kroku 4.  
  
     Metody, které používáte závisí na jaké webovou službu nabízí.  
  
6.  Přiřadit odpovědi data z webovou službu, která <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.  
  
 Při spuštění projektu ovládací prvky zobrazení ve zdroji dat na první záznam. Posouvání záznamů událostí měny pomocí objektů v můžete povolit <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources)   
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)  
  
  