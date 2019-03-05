---
title: Nepoužitých hodnot a parametrů
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 1ea80887fff6dcb1afba80feb782b23d1e790579
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325345"
---
# <a name="unused-expression-values-and-parameters"></a>Nepoužité výraz hodnoty a parametry

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Setmívá nepoužitých parametrů a vygeneruje upozornění pro nepoužívané výraz hodnoty.

**Kdy:** Máte parametry nebo výraz hodnoty, které se nikdy nepoužívá.

**Proč:** Někdy je obtížné určit, pokud hodnota nebo parametr je již nejsou déle používány. Tyto hodnoty mizení nebo pojmenováním upozornění, získáte vizuální upozornění jaké kódu můžete odstranit.

## <a name="unused-expression-values-and-parameters-diagnostic"></a>Nepoužité výraz hodnoty a parametry diagnostiky

1. Máte všechny hodnoty výrazu nebo parametr, který se nepoužívá.
2. Nepoužitý parametr se zobrazí vyblednout navýšení kapacity. Hodnota nevyužité výrazu se zobrazí upozornění.

  ![Nepoužitý parametr](media/unused-parameter.png)
  ![nepoužitých hodnot](media/unused-value.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
