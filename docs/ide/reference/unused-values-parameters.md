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
ms.openlocfilehash: afcf85fff188853890b86cf7deb13b2457f5e0b8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157695"
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
