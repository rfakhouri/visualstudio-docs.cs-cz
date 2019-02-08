---
title: Návrhář postupu provádění – dialogové okno Editor typu kolekce
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a6754c8264b68d8884f5e8ebaea763e004c71596
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913912"
---
# <a name="type-collection-editor-dialog-box"></a>Dialogové okno Editor typu kolekce

**Editor typu kolekce** dialogové okno umožňuje přidat známé typy, které **odeslat** a **Receive** aktivity. Toto dialogové okno se také používá k přidání argumentů obecného typu **InvokeMethod** aktivity. Když se použije pro **odeslat** a **Receive** aktivity přidat známé typy, **Editor typu kolekce** dialogovému oknu vyžaduje přidání typ být jedinečný. Pokud se přidá duplicitní typ a kliknutím se potvrzené změny **OK**, vrátí chybovou zprávu. Když se použije pro **InvokeMethod** aktivity přidáte argumenty obecného typu, **Editor typu kolekce** dialogové okno umožňuje přidání duplicitní typy.

Další informace najdete v tématu [známé typy kontraktů dat](/dotnet/framework/wcf/feature-details/data-contract-known-types).

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **kolekci typů** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|-|-----------------|
|**Seznam typů**|Seznam typů, které byly přidány nebo odebrány.|

## <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>Funkce přineste si Editor typu kolekce pro odesílání a příjem aktivity

1.  Vyberte **odeslat** nebo **Receive** aktivity v návrhovém zobrazení.

2.  Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.

3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **KnownTypes** vlastnost.

## <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>Chcete-li přenést až Editor kolekce typu aktivity InvokeMethod

1.  Vyberte **InvokeMethod** aktivity v návrhovém zobrazení.

2.  Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.

3.  V **vlastnosti** okna, klikněte na tlačítko se třemi tečkami vedle **parametry GenericTypeArguments** vlastnost.