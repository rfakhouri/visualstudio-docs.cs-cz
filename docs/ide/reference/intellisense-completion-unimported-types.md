---
title: Doplňování technologie IntelliSense pro neimportované typy
description: Jak používat doplňování technologie IntelliSense pro typy, které jste ještě neimportovali s `using` směrnice.
ms.date: 06/20/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: f313cfa8520e4c13b310be0f9223466c529ca18f
ms.sourcegitcommit: 16bcaca215de75479695738d3c2d703c78c3500e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2019
ms.locfileid: "67313209"
---
# <a name="intellisense-completion-for-unimported-types"></a>Doplňování technologie IntelliSense pro neimportované typy

Tento refaktoring platí pro:

- C#

**Co:** Technologie IntelliSense nabízí dokončování pro neimportované typy.

**Kdy:** Chcete přidat typ, který už má závislosti ve vašem projektu, ale příkaz import ještě nejsou přidané do souboru. 

**Proč:** Není nutné ručně přidejte příkaz importu do souboru.

## <a name="how-to"></a>Postupy

1. Jakmile začnete používat typ, který má závislosti ve vašem projektu, IntelliSense vám poskytne návrhy.
2. Stisknutím klávesy **kartu**. 

   Příkaz importu přidá do souboru.

   ![Doplňování technologie IntelliSense pro neimportované typy](media/intellisense-completion-unimported-types.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
