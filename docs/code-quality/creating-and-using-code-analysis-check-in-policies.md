---
title: "Vytváření a používání zásad vrácení se změnami analýzy kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, check-in policies
ms.assetid: 3fa5a849-e05f-4e31-8ba3-b014c889d94d
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a7d8ab4732938721da8e72c5a4c5f7387a4e67e2
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="creating-and-using-code-analysis-check-in-policies"></a>Vytváření a používání zásad vrácení se změnami Analýzy kódu
Pokud používáte Team Foundation verze ovládacího prvku (TFVC), můžete vytvořit zásady pro analýzu kódu vrácení se změnami pro rozhraní .NET Framework a nativní kód projektů (C/C++) v týmového projektu. Analýza vrácení se změnami zásad kódu můžete použít k řízení a zlepšení kvality kódu, který se změnami do základu kódu.  
  
 Zásady se předá, když je aktuální místní sestavení a spuštění analýzy kódu na nejnovější zdrojové soubory. Minimálně musí obsahovat pravidel analýzy kódu, které jsou povoleny v projektu kódu stejná pravidla jako ty, které jsou definovány v zásad vrácení se změnami týmového projektu. Pravidla, která byla zadaná jako chyby v nastavení projektu tým musí být zadaná také jako chyby v projektu kódu  
  
> [!IMPORTANT]
>  Nelze použít zásad vrácení se změnami analýzy kódu pro projekty webových stránek. Je možné použít pro projekty webových aplikací.  
  
 Zásad vrácení se změnami analýzy vytváření kódu pomocí nastavení projektu Team [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)]. Zadat a vynutit pro týmový projekt zásad vrácení se změnami, ale spustí analýzy kódu jsou konfigurovány a spustit pro jednotlivé kód projekty v počítačích se místní vývoj. Tato část popisuje, jak určit zásad analýzy kódu vrácení se změnami pro týmový projekt a způsob implementace vlastních zásad analýzy kódu pro spravovaný kód.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Vytváření nebo aktualizace standardních zásad vracení se změnami Analýzy kódu](../code-quality/how-to-create-or-update-standard-code-analysis-check-in-policies.md)  
 Vysvětluje kroky, které můžete použít k nastavení a upravit zásady pro analýzu kódu pro týmový projekt.  
  
 [Implementace vlastních zásad vrácení se změnami pro spravovaný kód](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)  
 Vysvětluje kroky, které použijete k vytvoření vlastního pravidla pro nastavení zásady vrácení se změnami týmového projektu a synchronizovat kód projekty týmový projekt pomocí zásad vrácení se změnami.  
  
 [Kompatibilita verzí pro zásady vracení se změnami Analýzy kódu](../code-quality/version-compatibility-for-code-analysis-check-in-policies.md)  
 Popisuje problémy s kompatibilitou vrácení se změnami analýzy kódu mezi verzemi [!INCLUDE[vstsLong](../code-quality/includes/vstslong_md.md)].  
  
 [Postupy: Přizpůsobení slovníku Analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
 Vysvětluje, jak přidat slova a tokeny do slovníku, který se odkazuje v pojmenování pravidel analýzy kódu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Zvýšení kvality kódu použitím zásad vracení se změnami týmového projektu](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)