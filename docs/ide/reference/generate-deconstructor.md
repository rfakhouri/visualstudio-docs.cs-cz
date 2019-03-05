---
title: Generovat deconstructor rychlá akce
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: a609b16e0d1bc7e30dc26ef047228a6cacdb46b2
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325291"
---
# <a name="generate-a-deconstructor-in-visual-studio"></a>Generování deconstructor v sadě Visual Studio

Tato generace kód platí pro:

- C#

**Co:** Umožňuje okamžitě generovat pahýl metody pro nové deconstructor.

**Kdy:** Chcete automaticky správně dekonstruovat typu.

**Proč:** Deconstructor, můžete zadat ručně, ale tato funkce bude generovat zástupná procedura za vás se správnými výstupní parametry.

## <a name="generate-deconstructor"></a>Generovat deconstructor

1. Deklarujte nový typ s požadovanou si zadanými parametry. Tato deklarace způsobí chybu, pokud žádná instance deconstruct najdete odpovídající vaší deklarace.

   ![Chybějící deconstructor chyba](media/deconstruct.png)

2. Dále proveďte jednu z následujících postupů v:

   - **Klávesnice**
      - Kurzor v vašeho prohlášení, stiskněte **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
   - **Myši**
      - Klikněte pravým tlačítkem a vyberte **rychlé akce a Refaktoringy** nabídky.
      - Klikněte na ![šroubovák](media/screwdriver.png) ikona, která se zobrazí u levého okraje, pokud textový kurzor na prázdný řádek ve třídě.

      ![Generovat deconstructor oprava kódu](media/deconstruct-codefix.png)

3. Vyberte **generovat metodu "MyInternalClass.Deconstruct"** ke generování deconstructor.

   ![Výsledný kód deconstructor](media/deconstruct-result.png)


## <a name="see-also"></a>Viz také:

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)