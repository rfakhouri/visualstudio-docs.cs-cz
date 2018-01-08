---
title: "Postupy: povolení a zákaz automatické analýzy kódu pro spravovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c22d194-5fea-4f23-b02d-19344fa64a64
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 198047196ba6f58c69736ef67352267845047b52
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Postupy: Povolení a zákaz automatické analýzy kódu pro spravovaný kód
Analýza kódu na spuštění před každé sestavení spravovaný projekt kódu můžete nakonfigurovat. Můžete nastavit různé vlastnosti analýzy kódu pro každou [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] konfigurace.  
  
### <a name="to-enable-or-disable-automatic-code-analysis"></a>K povolení nebo zákaz automatické analýzy kódu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V dialogovém okně Vlastnosti projektu klikněte na tlačítko **analýza kódu**.  
  
3.  Zadejte typ sestavení v **konfigurace** a cílová platforma v **platformy**.  
  
4.  Pokud chcete povolit nebo zakázat automatické analýzy kódu, zaškrtněte nebo zrušte **povolit analýza kódu v sestavení (definuje CODE_ANALYSIS konstanta)** zaškrtávací políčko.