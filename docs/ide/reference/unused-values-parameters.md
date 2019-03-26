---
title: Nepoužívané hodnoty a parametry
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 2d0875f9a298af24575cc05008713cbb6c3e2ead
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58414678"
---
# <a name="unused-value-assignments-variables-and-parameters"></a>Přiřazení nepoužitých hodnot, proměnné a parametry

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Setmívá nepoužitých parametrů a vygeneruje upozornění pro nepoužívané výraz hodnoty. Kompilátor také provádí analýzu toku k vyhledání všech přiřazení nepoužitých hodnot. Nepoužité zesvětlit přiřazení hodnoty a zobrazí se žárovka s [rychlá akce](../quick-actions.md) odebrat redundantní přiřazení. Nepoužité proměnné s zobrazit neznámé hodnoty [rychlá akce](../quick-actions.md) návrhem na použití [zahodí](/dotnet/csharp/discards) místo. (Zahození jsou dočasné a fiktivní proměnné, které nejsou používány záměrně v kódu aplikace. Mohou snížit přidělení paměti a aby byl váš kód lépe čitelný.)

**Kdy:** Máte přiřazení hodnoty, parametry nebo výraz hodnoty, které se nikdy nepoužívá.

**Proč:** Někdy je obtížné určit, pokud přiřazení hodnoty, proměnná nebo parametr je již nejsou déle používány. Tyto hodnoty mizení nebo generuje upozornění, získat vizuální upozornění jaké kódu můžete odstranit.

## <a name="unused-expression-values-and-parameters-diagnostic"></a>Nepoužité výraz hodnoty a parametry diagnostiky

1. Máte žádné přiřazení hodnoty, proměnná nebo parametr, který se nepoužívá.
2. Přiřazení nepoužitých hodnot nebo parametr, zobrazí se zašedlou navýšení kapacity. Hodnota výrazu nevyužité vygeneruje upozornění.

  ![Nepoužitý parametr](media/unused-parameter.png)
  ![nepoužitých hodnot](media/unused-value.png)
  ![nepoužitých hodnot přiřazení](media/unused-value-assignment.png)
  ![nepoužitých hodnot zahození](media/unused-value-discard.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
