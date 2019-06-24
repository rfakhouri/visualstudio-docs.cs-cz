---
title: Generovat parametr refaktoring
ms.date: 06/19/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e95e76c35afdb8cdbe38c8b33329734ba68361b1
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67329097"
---
# <a name="generate-parameter"></a>Generovat parametr

Tento refaktoring platí pro:

- C#

**Co:** Automaticky generuje parametr metody.

**Kdy:** Odkazujete na proměnnou v metodě, která neexistuje v aktuálním kontextu a obdrží chybu; Generovat parametr jako opravu kódu. 

**Proč:** Můžete rychle změnit podpis metody bez ztráty kontextu.

## <a name="how-to"></a>Postupy

1. Umístěte ukazatel myši v názvu proměnné a stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.
1. Vyberte **generovat parametr**.

   ![Generovat parametr](media/generate-parameter.png) 

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
