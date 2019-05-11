---
title: Generovat deconstructor rychlá akce
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 5a3a89d15d05b44575fede98d3043d706b24c1d9
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531888"
---
# <a name="generate-a-deconstructor-in-visual-studio"></a>Generování deconstructor v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** Umožňuje okamžitě generovat pahýl metody pro nové deconstructor.

**Kdy:** Chcete automaticky správně dekonstruovat typu.

**Proč:** Můžete zadat ručně deconstructor, ale tato funkce generuje zástupná procedura za vás se správnými výstupní parametry.

## <a name="generate-a-deconstructor"></a>Generování deconstructor

1. Deklarujte nový typ s požadovanou si zadanými parametry. Tato deklarace způsobí chybu při najdete žádná instance deconstruct odpovídající vaší deklarace.

   ![Chybějící deconstructor chyba](media/deconstruct.png)

2. Proveďte jednu z následujících kroků:

   - **Klávesnice**
      - Kurzor v vašeho prohlášení vyberte kombinaci kláves Ctrl +. aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Vyberte ![šroubovák](media/screwdriver.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na prázdný řádek ve třídě.

      ![Generovat deconstructor opravu kódu](media/deconstruct-codefix.png)

3. Vyberte **generovat metodu "MyInternalClass.Deconstruct"** ke generování deconstructor.

   ![Výsledný kód deconstructor](media/deconstruct-result.png)

## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../csharp-developer-productivity.md)