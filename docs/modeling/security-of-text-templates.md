---
title: Zabezpečení textových šablon
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d9906f3b8af624e1761b73c3338bad98b263aa9e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957179"
---
# <a name="security-of-text-templates"></a>Zabezpečení textových šablon
Textové šablony mají následující aspekty zabezpečení:

-   Textové šablony jsou citlivé na libovolný kód vložení.

-   Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není zabezpečený, může spustit škodlivý procesor direktiv.

## <a name="arbitrary-code"></a>Libovolný kód
 Při psaní šablonu možné vložit jakýkoli kód v rámci \<## > značky. To umožňuje libovolného kódu být spuštěn přímo z textové šablony.

 Ujistěte se, že získání šablony z důvěryhodných zdrojů. Ujistěte se, že varování koncové uživatele vaší aplikace není pro spouštění šablon, které nepochází z důvěryhodných zdrojů.

## <a name="malicious-directive-processor"></a>Škodlivý procesoru direktiv
 Modul šablon textu pracuje s hostiteli transformaci a jeden nebo více procesorů pro direktivy transformace textu šablony do výstupního souboru. Další informace najdete v tématu [proces transformace textových šablon](../modeling/the-text-template-transformation-process.md).

 Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není bezpečná, spustí se nebezpečí spuštění škodlivého procesor direktiv. Škodlivý procesor direktiv může poskytnout kód, který je spuštěn v `FullTrust` režimu při spuštění šablony. Pokud jste vytvořili hostitele transformace vlastní textových šablon, je nutné použít mechanismus zabezpečeného například registr pro modul najít procesory direktiv.