---
title: "Dialogové okno Editor kolekcí typ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 8e4b794a623c3a0218e44773da6bdb6c76612816
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="type-collection-editor-dialog-box"></a>Dialogové okno Editor typ kolekce
**Editor kolekce typ** dialogové okno se používá k přidání známé typy **odeslat** a **Receive** aktivity. Toto dialogové okno se také používá k přidání argumenty obecného typu pro **InvokeMethod** aktivity. Pokud se používá pro **odeslat** a **Receive** aktivit za účelem přidání známé typy **Editor kolekce typu** dialogové okno vyžaduje typ dodatky být jedinečný. Pokud je přidána duplicitní typ a tato změna se potvrdí kliknutím **OK**, se vrátí chybovou zprávu. Pokud se používá pro **InvokeMethod** aktivitu Přidat argumenty obecného typu **Editor kolekce typ** dialogové okno umožňuje přidání duplicitní typů.  
  
> [!NOTE]
>  [! ZAHRNOUT[crabout](/dotnet/framework/wcf/feature-details/data-contract-known-types).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **typ kolekce** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Seznam typů**|Seznam typů, které byly přidány nebo odebrány.|  
  
## <a name="to-bring-up-the-type-collection-editor"></a>Aby se kolekce Editor typů  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>K přineste si Editor kolekce typ pro odesílání a příjmu aktivity  
  
1.  Vyberte **odeslat** nebo **Receive** aktivity v zobrazení návrhu.  
  
2.  Stiskněte klávesu **F4** se zprovoznit **vlastnosti** okno.  
  
3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **KnownTypes** vlastnost.  
  
#### <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Aby se kolekce Editor typů InvokeMethod aktivity  
  
1.  Vyberte **InvokeMethod** aktivity v zobrazení návrhu.  
  
2.  Stiskněte klávesu **F4** se zprovoznit **vlastnosti** okno.  
  
3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **GenericTypeArguments** vlastnost.