---
title: Dialogové okno Editor typu kolekce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: be2e6bde6c25c1bb515ec3f017f14506c03a3a71
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697058"
---
# <a name="type-collection-editor-dialog-box"></a>Dialogové okno Editor typu kolekce
**Editor typu kolekce** dialogové okno umožňuje přidat známé typy, které **odeslat** a **Receive** aktivity. Toto dialogové okno se také používá k přidání argumentů obecného typu **InvokeMethod** aktivity. Když se použije pro **odeslat** a **Receive** aktivity přidat známé typy, **Editor typu kolekce** dialogovému oknu vyžaduje přidání typ být jedinečný. Pokud se přidá duplicitní typ a kliknutím se potvrzené změny **OK**, vrátí chybovou zprávu. Když se použije pro **InvokeMethod** aktivity přidáte argumenty obecného typu, **Editor typu kolekce** dialogové okno umožňuje přidání duplicitní typy.  
  
> [!NOTE]
> [!INCLUDE[crabout](../includes/crabout-md.md)] známé typy, najdete v článku [známé typy kontraktů dat](https://msdn.microsoft.com/library/1a0baea1-27b7-470d-9136-5bbad86c4337).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **kolekci typů** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Seznam typů**|Seznam typů, které byly přidány nebo odebrány.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Chcete-li přenést až Editor typu kolekce  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Funkce přineste si Editor typu kolekce pro odesílání a příjem aktivity  
  
1. Vyberte **odeslat** nebo **Receive** aktivity v návrhovém zobrazení.  
  
2. Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.  
  
3. V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **KnownTypes** vlastnost.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Chcete-li přenést až Editor kolekce typu aktivity InvokeMethod  
  
1. Vyberte **InvokeMethod** aktivity v návrhovém zobrazení.  
  
2. Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.  
  
3. V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **parametry GenericTypeArguments** vlastnost.