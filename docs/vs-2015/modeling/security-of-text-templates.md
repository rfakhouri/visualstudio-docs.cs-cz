---
title: Zabezpečení textových šablon | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ce0a5b008df683694a20cce360fbd5e779e408d8
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54835033"
---
# <a name="security-of-text-templates"></a>Zabezpečení textových šablon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Textové šablony mají následující aspekty zabezpečení:  
  
-   Textové šablony jsou citlivé na libovolný kód vložení.  
  
-   Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není zabezpečený, může spustit škodlivý procesor direktiv.  
  
## <a name="arbitrary-code"></a>Libovolný kód  
 Při psaní šablonu možné vložit jakýkoli kód v rámci \<## > značky. To umožňuje libovolného kódu být spuštěn přímo z textové šablony.  
  
 Ujistěte se, že získání šablony z důvěryhodných zdrojů. Ujistěte se, že varování koncové uživatele vaší aplikace není pro spouštění šablon, které nepochází z důvěryhodných zdrojů.  
  
## <a name="malicious-directive-processor"></a>Škodlivý procesoru direktiv  
 Modul šablon textu pracuje s hostiteli transformaci a jeden nebo více procesorů pro direktivy transformace textu šablony do výstupního souboru. Další informace najdete v tématu [proces transformace textových šablon](../modeling/the-text-template-transformation-process.md).  
  
 Pokud mechanismus, který hostitel používá k vyhledání procesoru direktiv není bezpečná, spustí se nebezpečí spuštění škodlivého procesor direktiv. Škodlivý procesor direktiv může poskytnout kód, který je spuštěn v `FullTrust` režimu při spuštění šablony. Pokud jste vytvořili hostitele transformace vlastní textových šablon, je nutné použít mechanismus zabezpečeného například registr pro modul najít procesory direktiv.
