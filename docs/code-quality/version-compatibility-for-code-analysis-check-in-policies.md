---
title: Kompatibilita verzí pro zásady vracení se změnami Analýzy kódu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0fc164dea10a74bbff725ee153f298c820f1c203
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936444"
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>Kompatibilita verzí pro zásady vracení se změnami Analýzy kódu

Pokud se musí vyhodnotit a vytváření zásad analýzy kódu vrácení se změnami pomocí různých verzí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], musíte znát rozdíly v tom [!INCLUDE[vstsTfsOrcasLong](../code-quality/includes/vststfsorcaslong_md.md)] a [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] vyhodnocení zásad vrácení se změnami.

## <a name="version-compatibility-for-evaluating-check-in-policies"></a>Kompatibilita verzí pro vyhodnocení zásad vrácení se změnami

- Když se vyhodnocují Zásady vracení se změnami analýzy kódu v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], všechna pravidla, které existovaly ve [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] , ale neexistuje v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] jsou ignorovány.

- Když se vyhodnocují Zásady vracení se změnami analýzy kódu v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], všechna nová pravidla, které jsou výhradně [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] jsou ignorovány.

- Pokud zásady vrácení se změnami kód analýzy určuje pravidla sestavení [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] ignoruje všechna pravidla, která jsou určena podle sestavení, nebylo rozpoznáno.

- Pokud zásady vrácení se změnami kód analýzy určuje pravidla sestavení, která [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] nerozpozná, zobrazí se zpráva.

## <a name="version-compatibility-for-authoring-check-in-policies"></a>Kompatibilita verzí pro vytváření zásad vrácení se změnami

- Pokud jste vytvořili zásady analýzy kódu vrácení se změnami pomocí [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] verzi [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], nelze použít [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] verzi [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] jej upravit. A navíc [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] zásad se nedá vyhodnotit.

- Pokud jste vytvořili zásady analýzy kódu vrácení se změnami pomocí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], můžete použít [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] chcete upravit a zásady mohou také být vyhodnocena [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]. Po úpravě zásad s použitím [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], zásady nemůžete nadále upravovat pomocí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]. [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] vyhodnotit zásady bez problémů s neodpovídající silných názvů.

- Chcete-li vytvořit zásady analýzy kódu vrácení se změnami pomocí nastavení pravidel, které platí pro obě [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] a [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], musíte vytvořit zásady [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], proveďte všechny potřebné změny a uložte zásadu. Pokud existují změny pravidel pouze v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], upravte a uložte zásadu v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)].

   Po uložení zásady v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], už můžete změnit nastavení pro pravidla, které existují v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] pouze.