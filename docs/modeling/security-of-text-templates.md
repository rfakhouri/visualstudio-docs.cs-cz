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
ms.openlocfilehash: 66159516c6b1360203130dedb56c0e6c192a118a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050008"
---
# <a name="security-of-text-templates"></a>Zabezpečení textových šablon
Textové šablony mají následující aspekty zabezpečení:

- Textové šablony jsou citlivé na libovolný kód vložení.

- Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není zabezpečený, může spustit škodlivý procesor direktiv.

## <a name="arbitrary-code"></a>Libovolný kód
 Při psaní šablonu možné vložit jakýkoli kód v rámci \<## > značky. To umožňuje libovolného kódu být spuštěn přímo z textové šablony.

 Ujistěte se, že získání šablony z důvěryhodných zdrojů. Ujistěte se, že varování koncové uživatele vaší aplikace není pro spouštění šablon, které nepochází z důvěryhodných zdrojů.

## <a name="malicious-directive-processor"></a>Škodlivý procesoru direktiv
 Modul šablon textu pracuje s hostiteli transformaci a jeden nebo více procesorů pro direktivy transformace textu šablony do výstupního souboru. Další informace najdete v tématu [proces transformace textových šablon](../modeling/the-text-template-transformation-process.md).

 Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není bezpečná, spustí se nebezpečí spuštění škodlivého procesor direktiv. Škodlivý procesor direktiv může poskytnout kód, který je spuštěn v `FullTrust` režimu při spuštění šablony. Pokud jste vytvořili hostitele transformace vlastní textových šablon, je nutné použít mechanismus zabezpečeného například registr pro modul najít procesory direktiv.