---
title: "Generovat přepsání – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d2972cfe2ea4481ab8f5eab6284277615d1d64a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="generate-an-override-in-c"></a>Generovat přepsání v jazyce C# #
**Co:** umožňuje okamžitě generování kódu všechny metody, které je možné přepsat ze základní třídy. 

**Kdy:** chcete přepsat metodu základní třídy a automaticky generovat podpis.  

**Důvod:** můžete napsat podpis metody sami, ale tato funkce bude automaticky generovat podpis. 

**Postupy:**

1. Typ **přepsat** – klíčové slovo následované mezerou, kde chcete vložit podpisu přepsaného metoda a zobrazí rozevírací seznam IntelliSense.

   ![Přepsání IntelliSense](media/override_intellisense.png)

1. Vyberte metodu, kterou chcete přepsat ze základní třídy kliknutím na tlačítko pomocí myši nebo navigace k němu pomocí klávesnice a stiskněte **Enter**.

   >[!TIP]
   >* Použijte ikonu vlastnost ![Ikona vlastností](media/override_property.png) Chcete-li zobrazit nebo skrýt vlastnosti v seznamu.
   >* Použijte ikonu – metoda ![Ikona vlastností](media/override_method.png) Chcete-li zobrazit nebo skrýt metody v seznamu.

1. Vybrané metody nebo vlastnosti se zařadí do třídy jako přepsání, připraveno k implementaci.

   ![Přepsání výsledek](media/override_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
