---
title: "Generovat přepsání metody v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: df0eecdeb2aad15e1da68cef3b125c3c95f57e78
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generate-an-override-in-visual-studio"></a>Generovat přepsání v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu pro libovolné metody, které je možné přepsat ze základní třídy.

**Kdy:** chcete přepsat metodu základní třídy a automaticky generovat podpis.

**Důvod:** můžete napsat podpis metody sami, ale tato funkce bude automaticky generovat podpis.

## <a name="how-to"></a>Postupy

1. Typ `override` v jazyce C# nebo `Overrides` v jazyce Visual Basic následované mezerou, kam chcete vložit metodu přepsat.

   - C#:

    ![Přepsání IntelliSense C#](media/override-intellisense-cs.png)

   - Visual Basic:

    ![Přepsání jazyka Visual Basic IntelliSense](media/override-intellisense-vb.png)

1. Vyberte metodu, kterou chcete přepsat ze základní třídy.

   > [!TIP]
   > - Použijte ikonu vlastnost ![Ikona vlastností](media/override-property-cs.png) Chcete-li zobrazit nebo skrýt vlastnosti v seznamu.
   > - Použijte ikonu – metoda ![Ikona – metoda](media/override-method-cs.png) Chcete-li zobrazit nebo skrýt metody v seznamu.

   Vybrané metody nebo vlastnosti je přidat do třídy jako přepsání, připraveno k implementaci.

   - C#:

      ![Přepsání výsledek C#](media/override-result-cs.png)

   - Visual Basic:

      ![Přepsání výsledek jazyka Visual Basic](media/override-result-vb.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)
