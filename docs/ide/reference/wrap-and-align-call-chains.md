---
title: Zalamovat a zarovnávat řetězy volání
description: Naučte se zalamovat a zarovnávat řetězce volání metod.
ms.date: 08/13/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 2a5b6bea4c915e029ca3ae448444decce0d7b041
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2019
ms.locfileid: "69619738"
---
# <a name="wrap-and-align-call-chains"></a>Zalamovat a zarovnávat řetězy volání

Tento refaktoring platí pro:

- C#

**Co:** Umožňuje zalamovat a zarovnávat řetězce volání metod.

**Kdy:** Máte dlouhý řetěz skládající se z několika volání metod v jednom příkazu.

**Proč:** Čtení dlouhého seznamu je snazší, když se zabalí nebo odsadí podle preferencí uživatele.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor do libovolného řetězce volání.
2. Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
3. Chcete-li přijmout refaktoring, vyberte možnost zabalení **řetězu volání** nebo **zabalení a zarovnání řetězce volání** .

   ![Zalamovat a zarovnávat řetězy volání](media/wrap-call-chain.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
