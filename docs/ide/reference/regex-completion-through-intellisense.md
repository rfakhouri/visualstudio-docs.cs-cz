---
title: Regulární výraz dokončení prostřednictvím nabídky technologie IntelliSense
ms.date: 06/10/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 75110432f9bba35ce02588032b9a41dece01056b
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67033411"
---
# <a name="regex-completion-through-intellisense-menu"></a>Regulární výraz dokončení prostřednictvím nabídky technologie IntelliSense

Tento refaktoring platí pro:

- C#

**Co:** Dokončení regulárních výrazů (regex) prostřednictvím nabídky technologie IntelliSense.

**Kdy:** Chcete zadat regulární výraz s pomocí od technologie IntelliSense. Technologie IntelliSense umožňuje základní dokončení a vysvětlení, co jednotlivé znaky střední regulární výraz. 

**Proč:** Zápis regulární výraz je obtížné a technologie IntelliSense můžete zapsat.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor string regulárního výrazu.
2. Stisknutím klávesy **Ctrl**+**místo** k aktivační události **IntelliSense** nabídky.
3. Vyberte znak, který chcete přidat do vaší string regulárního výrazu.

   ![Regulární výraz doplňování IntelliSense](../media/regex-completion-intellisense.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
