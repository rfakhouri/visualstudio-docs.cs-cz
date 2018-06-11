---
title: 'Postupy: naplnění dokumentů daty z objektů'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- data [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5a7dee9c56b454ad7d9213817c62b0ea4fbe7c8c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255746"
---
# <a name="how-to-populate-documents-with-data-from-objects"></a>Postupy: naplnění dokumentů daty z objektů
  Accesing data v datovém objektu funguje stejným způsobem jako v projekty na úrovni dokumentu pro aplikaci Microsoft Office Word stejně jako ve Windows Forms projekty. Použít stejnou nástroje a kódu přenést data z objektu do vašeho řešení a ovládací prvky Windows Forms můžete použít k zobrazení dat. Kromě toho můžete zobrazit data pomocí hostitelské ovládací prvky. Hostitelské ovládací prvky jsou nativní objekty v aplikaci Microsoft Office Word, které vylepšily se události a možnosti data vazby. Další informace najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Musíte provést tři základní kroky k naplnění dokumentů daty z objektu:  
  
-   Přidání ovládacího prvku v dokumentu, který můžete vázat na data.  
  
-   Přidáte datový objekt k dokumentu.  
  
-   Připojte datový objekt k BindingSource.   
  
## <a name="add-a-data-object"></a>Přidat datový objekt  
  
### <a name="to-add-a-data-object"></a>Chcete-li přidat datový objekt  
  
-   Otevřete **zdroje dat** okno a vytvořte zdroj dat z objektu. Další informace najdete v tématu [přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources).  
  
## <a name="connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k BindingSource  
 V projekty na úrovni dokumentu přidání ovládacích prvků do dokumentu a jejich vazby na data v době návrhu.  
  
 V doplňku VSTO projekty vytvořit ovládací prvky a navázat je za běhu.  
  
### <a name="document-level-projects"></a>Projekty na úrovni dokumentu  
  
#### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k BindingSource  
  
1.  Přetáhněte pole dat, který chcete z **zdroje dat** okna dokumentu. Tím se automaticky vytvoří ovládacího prvku.  
  
2.  V kódu vytvořte instanci typu objektu, který jste zvolili pro zdroj dat.  
  
3.  Přiřadit instanci systému na <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.  
  
### <a name="application-level-projects"></a>Projekty na úrovni aplikace  
  
#### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k BindingSource  
  
1.  V kódu vytvoření instance typu objektu, která je přidružená ke zdroji dat.  
  
2.  Vytvoření instance <xref:System.Windows.Forms.BindingSource>.  
  
3.  Přiřadit instance zdroje dat na <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.  
  
4.  Přidejte tento zdroj dat jako datové vazby na ovládací prvek.  
  
## <a name="see-also"></a>Viz také:  
 
 [Přidat nové zdroje dat](/visualstudio/data-tools/add-new-data-sources)   
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)
 
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Připojte se k datům v aplikacích Windows Forms](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  