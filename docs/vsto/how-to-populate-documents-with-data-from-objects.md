---
title: "Postupy: naplnění dokumentů daty z objektů | Microsoft Docs"
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
- data [Office development in Visual Studio], adding to documents
ms.assetid: 83e6ebac-e468-4bef-a91c-78c7bf597a75
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 418e56c83a463c10d9dfc990236315751e07c000
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-populate-documents-with-data-from-objects"></a>Postupy: Naplnění dokumentů daty z objektů
  Accesing data v datovém objektu funguje stejným způsobem jako v projekty na úrovni dokumentu pro aplikaci Microsoft Office Word stejně jako ve Windows Forms projekty. Použít stejnou nástroje a kódu přenést data z objektu do vašeho řešení a ovládací prvky Windows Forms můžete použít k zobrazení dat. Kromě toho můžete zobrazit data pomocí hostitelské ovládací prvky. Hostitelské ovládací prvky jsou nativní objekty v aplikaci Microsoft Office Word, které vylepšily se události a možnosti data vazby. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Musíte provést tři základní kroky k naplnění dokumentů daty z objektu:  
  
-   Přidání ovládacího prvku v dokumentu, který můžete vázat na data.  
  
-   Přidáte datový objekt k dokumentu.  
  
-   Připojte datový objekt k BindingSource.   
  
## <a name="adding-a-data-object"></a>Přidání dat objektu  
  
#### <a name="to-add-a-data-object"></a>Chcete-li přidat datový objekt  
  
-   Otevřete **zdroje dat** okno a vytvořte zdroj dat z objektu. Další informace najdete v tématu [přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources).  
  
## <a name="connecting-the-data-object-to-the-bindingsource"></a>Datový objekt propojíte BindingSource  
 V projekty na úrovni dokumentu přidání ovládacích prvků do dokumentu a jejich vazby na data v době návrhu.  
  
 V doplňku VSTO projekty vytvořit ovládací prvky a navázat je za běhu.  
  
### <a name="document-level-projects"></a>Projekty na úrovni dokumentu  
  
##### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k BindingSource  
  
1.  Přetáhněte pole dat, který chcete z **zdroje dat** okna dokumentu. Tím se automaticky vytvoří ovládacího prvku.  
  
2.  V kódu vytvořte instanci typu objektu, který jste zvolili pro zdroj dat.  
  
3.  Přiřadit instanci systému na <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.  
  
### <a name="application-level-projects"></a>Projekty na úrovni aplikace  
  
##### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k BindingSource  
  
1.  V kódu vytvoření instance typu objektu, která je přidružená ke zdroji dat.  
  
2.  Vytvoření instance <xref:System.Windows.Forms.BindingSource>.  
  
3.  Přiřadit instance zdroje dat na <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.  
  
4.  Přidejte tento zdroj dat jako datové vazby na ovládací prvek.  
  
## <a name="see-also"></a>Viz také  
 
 [Přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources)   
 [Vytvoření vazby ovládacích prvků Windows Forms k datům ve Visual Stduio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)
 
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Připojování k datům v aplikacích Windows Forms](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  