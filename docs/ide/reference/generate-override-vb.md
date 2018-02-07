---
title: "Generovat přepsání – generování kódu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 334f5a79dad1b7d2c14768d0698797a34ad039c5
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="generate-an-override-in-visual-basic"></a>Generovat přepsání v jazyce Visual Basic
**Co:** umožňuje okamžitě generování kódu všechny metody, které je možné přepsat ze základní třídy. 

**Kdy:** chcete přepsat metodu základní třídy a automaticky generovat podpis.  

**Důvod:** můžete napsat podpis metody sami, ale tato funkce bude automaticky generovat podpis. 

**Postupy:**

1. Typ **přepsání** – klíčové slovo následované mezerou, kde chcete vložit podpisu přepsaného metoda a zobrazí rozevírací seznam IntelliSense.

   ![Přepsání IntelliSense](media/override-intellisense-vb.png)

1. Vyberte metodu, kterou chcete přepsat ze základní třídy kliknutím na tlačítko pomocí myši nebo navigace k němu pomocí klávesnice a stiskněte **Enter**.

<!--
   >[!TIP]
   >* Use the Property icon ![Property icon](media/override-property-vb.png) to show or hide  Properties in the list.
   >* Use the Method icon ![Property icon](media/override-method-vb.png) to show or hide Methods in the list.
-->

1. Vybrané metody nebo vlastnosti se zařadí do třídy jako přepsání, připraveno k implementaci.

   ![Přepsání výsledek](media/override-result-vb.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md) 