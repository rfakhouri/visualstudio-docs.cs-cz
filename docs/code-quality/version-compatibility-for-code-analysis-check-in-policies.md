---
title: "Kompatibilita verzí pro zásady vrácení se změnami analýzy kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 323024cdb420d48c40b7a676bc4e698af7622b67
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>Kompatibilita verzí pro zásady vracení se změnami Analýzy kódu
Pokud se musí vyhodnotit a vytváření zásad analýzy kódu vrácení se změnami pomocí různých verzích [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], musíte znát rozdíly v tom [!INCLUDE[vstsTfsOrcasLong](../code-quality/includes/vststfsorcaslong_md.md)] a [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] vyhodnocení zásad vrácení se změnami.  
  
## <a name="version-compatibility-for-evaluating-check-in-policies"></a>Kompatibilita verzí pro vyhodnocení zásad vrácení se změnami  
  
-   Když jsou vyhodnocovány zásad vrácení se změnami analýzy kódu v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], všechna pravidla, které existovaly v sadě [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] , ale nejsou k dispozici v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] jsou ignorovány.  
  
-   Když jsou vyhodnocovány zásad vrácení se změnami analýzy kódu v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], všechny nové pravidel, která jsou výhradně pro [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] jsou ignorovány.  
  
-   Pokud zásady vrácení se změnami kódu analysis určuje pravidla sestavení [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] ignoruje všechna pravidla, které jsou určené sestavení, nelze rozpoznat.  
  
-   Je-li zásad vrácení se změnami kódu analysis určuje pravidla sestavení, [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] nerozpozná, zobrazí se zpráva.  
  
## <a name="version-compatibility-for-authoring-check-in-policies"></a>Kompatibilita verzí pro vytváření zásad vrácení se změnami  
  
-   Pokud jste vytvořili zásady pro analýzu kódu vrácení se změnami pomocí [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] verzi [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], nemůžete použít [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] verzi [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] jej upravit. A navíc [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] nelze vyhodnotit zásadu.  
  
-   Pokud jste vytvořili zásady pro analýzu kódu vrácení se změnami pomocí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], můžete použít [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] změnit a zásady můžete taky vyhodnocení [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)]. Po úpravě zásad pomocí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], zásady už můžete upravit pomocí [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]. [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)]můžete vyhodnotit zásady bez problémů s odlišnými silné názvy.  
  
-   K vytvoření zásad vrácení se změnami kódu analysis s nastavením pravidlo, které platí pro obě [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] a [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], musíte vytvořit zásadu v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)], proveďte všechny potřebné změny a uložení zásady. Pokud existují změny pravidel pouze v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], upravit a uložit zásadu v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)].  
  
     Po uložení zásady v [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)], už můžete změnit nastavení pro pravidla, které existují v [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] pouze.