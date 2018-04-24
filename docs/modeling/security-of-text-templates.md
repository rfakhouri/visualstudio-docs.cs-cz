---
title: Zabezpečení textových šablon
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 97827a9219edbed08554aaedf1ebb8c0397606d5
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="security-of-text-templates"></a>Zabezpečení textových šablon
Textové šablony mají následující potížích se zabezpečením:

-   Textové šablony jsou citlivé na libovolný kód vložení.

-   Pokud mechanismus, který hostitel používá k nalezení procesoru direktiv není zabezpečený, může spustit škodlivý procesoru direktiv.

## <a name="arbitrary-code"></a>Libovolný kód
 Když píšete šablonu, můžete vložit žádný kód v rámci \<## > značky. To umožňuje v rámci textové šablony provést z libovolného kódu.

 Ujistěte se, že získat šablony z důvěryhodných zdrojů. Ujistěte se, že upozornit koncovým uživatelům vaší aplikace není k provedení šablony, které nepocházejí z důvěryhodných zdrojů.

## <a name="malicious-directive-processor"></a>Škodlivý procesoru direktiv
 Text šablony modul komunikuje se službou hostitel transformaci a jeden nebo více procesory direktiv k transformaci text šablony do výstupního souboru. Další informace najdete v tématu [proces transformace textových šablon](../modeling/the-text-template-transformation-process.md).

 Pokud mechanismus, který hostitel používá k nalezení procesoru direktiv nejsou zabezpečené, spustí se nebezpečí spuštění škodlivého procesoru direktiv. Škodlivý procesoru direktiv může poskytnout kód, který běží v `FullTrust` režimu při spuštění šablony. Pokud vytvoříte vlastního hostitele textových šablon transformace, je nutné použít zabezpečený mechanismus, například registr pro modul vyhledat procesory direktiv.