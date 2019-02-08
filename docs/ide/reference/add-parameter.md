---
title: Přidání parametru do metody rychlá akce
ms.date: 09/28/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3e1461afe5c4d6026f8532896ba837e971fed652
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55934351"
---
# <a name="add-a-parameter-to-a-method-using-a-quick-action"></a>Přidání parametru k metodě pomocí rychlé akce

Tato generace kód platí pro:

- C#

- Visual Basic

**Co:** Umožňuje automaticky přidat parametr do metody, na základě využití.

**Kdy:** Musíte přidat parametr do metody a chcete správně deklarujte ho automaticky.

**Proč:** Můžete přidat parametr do deklarace metody před voláním, ale tato funkce doplňuje že ho automaticky podle volání metody.

## <a name="how-to-use-it"></a>Jak ji použít

1. Přidejte volání metody nadbytečný argument.

   Červený "podtržení" se zobrazí pod název metody, kde volání.

2. Umístěte ukazatel na červenou "podtržení" se zobrazí nabídky rychlé akce. Vyberte **šipka dolů** na nabídky rychlé akce a potom vyberte **přidání parametru do [metoda]**.

   ![Přidání parametru do metody rychlé akce v sadě Visual Studio](media/add-parameter-to-method.png)

   > [!TIP]
   > Nabídky rychlé akce se můžete dostat taky tím, že umístíte kurzor na řádek volání metody a pak buď stisknutím klávesy **Ctrl**+**.** nebo vyberte ikonu žárovky na okraji souboru.

   Visual Studio přidá nový parametr deklarace metody.

> [!NOTE]
> Pokud máte další volání metody může vytvářejí chyby po použití této rychlé akce, protože, nezadávejte argument pro parametr nově přidané.

## <a name="see-also"></a>Viz také:

- [Přidat parametr do konstruktoru](generate-constructor.md#addparameter)