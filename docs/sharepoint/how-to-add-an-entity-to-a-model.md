---
title: "Postupy: Přidání Entity do modelu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EntityTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2ef3885f2a290fd1d4193daf9436a08ae5588a0d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-entity-to-a-model"></a>Postupy: Přidání entity do modelu
  Pokud chcete vytvořit entitu, přidání ovládacího prvku entity ze sady Visual Studio **sada nástrojů** do návrháře Business Data Connectivity (BDC).  
  
### <a name="to-add-an-entity-to-the-model"></a>Přidání entity do modelu  
  
1.  Vytvoření projektu BDC nebo otevřít existující projekt BDC. Další informace najdete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
2.  V **sada nástrojů**, z **BusinessDataCatalog** skupiny, přidejte **Entity** ovládacího prvku do návrháře.  
  
     Nová entita, zobrazí se v designeru. Visual Studio. přidá `<Entity>` element XML souboru modelu služby BDC do projektu. Další informace o atributech Entity element najdete v tématu [Entity](http://go.microsoft.com/fwlink/?LinkId=169296).  
  
3.  V designeru, otevřete místní nabídky pro entitu, zvolte **přidat**a potom zvolte **identifikátor**.  
  
     Nový identifikátor se zobrazí u entity.  
  
    > [!NOTE]  
    >  Můžete změnit název entity a identifikátoru v **vlastnosti** okno.  
  
4.  Definování polí entity v třídě. Můžete buď přidejte novou třídu do projektu, nebo použijte existující třídy vytvořené pomocí jiných nástrojů, například Návrhář relací objektů (Návrhář relací objektů). Následující příklad ukazuje třídu entity s názvem kontaktu.  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)   
 [Postupy: přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)   
 [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)   
 [Postupy: přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)   
 [Postupy: Přidání specifické vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  