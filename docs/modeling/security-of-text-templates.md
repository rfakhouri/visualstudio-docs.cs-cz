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
ms.prod: visual-studio-dev15
ms.openlocfilehash: 94b2520ffafe3e99420bf77577b59341b6d216aa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957205"
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