---
title: Kompatibilita verzí pro Zásady vracení se změnami analýzy kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a63ead03baffaa0ce8047220ff1ce8a33c88be8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201182"
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>Kompatibilita verzí pro zásady vracení se změnami Analýzy kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud se musí vyhodnotit a vytváření zásad analýzy kódu vrácení se změnami pomocí různých verzí [!INCLUDE[esprtfc](../includes/esprtfc-md.md)], musíte znát rozdíly v tom [!INCLUDE[vstsTfsOrcasLong](../includes/vststfsorcaslong-md.md)] a [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] vyhodnocení zásad vrácení se změnami.  
  
## <a name="version-compatibility-for-evaluating-check-in-policies"></a>Kompatibilita verzí pro vyhodnocení zásad vrácení se změnami  
  
- Když se vyhodnocují Zásady vracení se změnami analýzy kódu v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], všechna pravidla, které existovaly ve [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] , ale neexistuje v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] jsou ignorovány.  
  
- Když se vyhodnocují Zásady vracení se změnami analýzy kódu v [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)], všechna nová pravidla, které jsou výhradně [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] jsou ignorovány.  
  
- Pokud zásady vrácení se změnami kód analýzy určuje pravidla sestavení [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] ignoruje všechna pravidla, která jsou určena podle sestavení, nebylo rozpoznáno.  
  
- Pokud zásady vrácení se změnami kód analýzy určuje pravidla sestavení, která [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] nerozpozná, zobrazí se zpráva.  
  
## <a name="version-compatibility-for-authoring-check-in-policies"></a>Kompatibilita verzí pro vytváření zásad vrácení se změnami  
  
- Pokud jste vytvořili zásady analýzy kódu vrácení se změnami pomocí [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] verzi [!INCLUDE[esprtfc](../includes/esprtfc-md.md)], nelze použít [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] verzi [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] jej upravit. A navíc [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] zásad se nedá vyhodnotit.  
  
- Pokud jste vytvořili zásady analýzy kódu vrácení se změnami pomocí [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] v [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)], můžete použít [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)] chcete upravit a zásady mohou také být vyhodnocena [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]. Po úpravě zásad s použitím [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], zásady nemůžete nadále upravovat pomocí [!INCLUDE[esprtfc](../includes/esprtfc-md.md)] v [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]. [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] vyhodnotit zásady bez problémů s neodpovídající silných názvů.  
  
- Chcete-li vytvořit zásady analýzy kódu vrácení se změnami pomocí nastavení pravidel, které platí pro obě [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] a [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], musíte vytvořit zásady [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)], proveďte všechny potřebné změny a uložte zásadu. Pokud existují změny pravidel pouze v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], upravte a uložte zásadu v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)].  
  
     Po uložení zásady v [!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)], už můžete změnit nastavení pro pravidla, které existují v [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] pouze.
