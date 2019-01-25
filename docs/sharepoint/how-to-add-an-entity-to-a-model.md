---
title: 'Postupy: Přidání Entity do modelu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- EntityTool
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b269bb18580784fb08d9b081a37935c7b3f37627
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864657"
---
# <a name="how-to-add-an-entity-to-a-model"></a>Postupy: Přidání entity do modelu
  Jak vytvořit entitu, přidejte ovládací prvek entity ze sady Visual Studio **nástrojů** na Návrhář obchodních dat připojení (BDC).  
  
### <a name="to-add-an-entity-to-the-model"></a>Přidání entity do modelu  
  
1.  Vytvoření projektu BDC nebo otevřete existující projekt služby BDC. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
2.  V **nástrojů**, z **BusinessDataCatalog** skupině, přidejte **Entity** ovládacího prvku do návrháře.  
  
     Nová entita se zobrazí v návrháři. Visual Studio přidá `<Entity>` elementu XML souboru modelu služby BDC do projektu. Další informace o atributech elementu Entity najdete v tématu [Entity](http://go.microsoft.com/fwlink/?LinkId=169296).  
  
3.  V Návrháři otevřete místní nabídku pro entitu, zvolte **přidat**a klikněte na tlačítko **identifikátor**.  
  
     Nový identifikátor se zobrazí v entitě.  
  
    > [!NOTE]  
    >  Můžete změnit název entity a identifikátoru **vlastnosti** okna.  
  
4.  Definujte pole entity ve třídě. Můžete buď přidejte novou třídu do projektu, nebo použijte existující třídy vytvořené pomocí jiných nástrojů, jako je například Návrhář relací objektů (O/R Designer). Následující příklad ukazuje třídu entity s názvem kontaktu.  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)  
