---
title: "Analýza kvality spravovaného kódu pomocí nástroje Analýza kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis,managed code
- managed code analyis
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 2008ac649302d87cc2d45274de3fdb1981aa571d
ms.sourcegitcommit: 9a2f937e42305db6e3eaa7aadc235b0ba9aafc83
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/31/2018
---
# <a name="analyzing-managed-code-quality-by-using-code-analysis"></a>Analýza kvality spravovaného kódu pomocí nástroje Analýza kódu
Chcete-li zjistit možná rizika v kódu, jako je například nezabezpečený přístup k datům, narušení ochrany použití a problémy návrhu, můžete použít nástroje pro analýzu kódu sady Visual Studio. Analýza kódu funguje na rozhraní .NET Framework, nativní (C a C++) a databázových aplikací. Analýza kódu pro spravovaný kód organizuje pravidla v *sad pravidel* cílených konkrétní kódování problémy.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Obecné úlohy|Podpůrný obsah|  
|------------------|------------------------|  
|**Získání praktické zkušenosti:** seznámíte se základy analýza kódu za účelem opravy závad v jednoduchou aplikaci pro rozhraní .NET Framework.|-   [Návod: Analýza spravovaného kódu na výskyt závad v kódu](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|  
|**Konfigurace analýzy kódu pro projekt:** pravidla pro spravovaný kód jsou uspořádány do sady pravidel, které cílí určité oblasti, například zabezpečení a návrhu. Můžete použít jednu z Microsoft nastaví standardní pravidla nebo vytvořit vlastní.|-   [Analýza kódu pro spravovaný kód – přehled](../code-quality/code-analysis-for-managed-code-overview.md)<br />-   [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)<br />-   [Potlačení upozornění použitím atributu SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|  
|**Spuštění analýzy kódu:** zadáte analýza kódu, které se mají automaticky pokaždé, když je sestavena konfigurace projektu a analýza kódu můžete spustit ručně na projektu.|-   [Postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)<br />-   [Postupy: ruční spuštění analýzy kódu](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|  
|**Analyzujte výsledky analýzy kódu:** upozornění analýzy kódu a chyb jsou uvedeny v okně nástroje Analýza kódu. Můžete vybrat upozornění nebo při nadpisu a zobrazte další informace o upozornění a k zobrazení a zvýrazněte řádek zdrojového kódu, který aktivováno pravidlo. Můžete použít id upozornění zobrazíte podrobné informace v knihovně MSDN, který obsahuje informace a příklady, jak k vyřešení problému.|-   [Postupy: zobrazování defektů spravovaného kódu](../code-quality/how-to-view-managed-code-defects.md)<br />-   [Analýza kódu pro spravovaný kód upozornění](../code-quality/code-analysis-for-managed-code-warnings.md)<br />-   [Upozornění podle CheckId](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [Anonymní metody a analýza kódu](../code-quality/anonymous-methods-and-code-analysis.md)|  
|**Analýza kódu integrovat váš životního cyklu vývoj:** zásad vrácení se změnami v [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)] povolit vývojové týmy a ujistěte se, že všechny code vrácení se změnami splňovat společnou sadu standardy analýzy kódu. Vytvoření pracovní položky pro porušení pravidel analýzy kódu je jednoduchý postup, který můžete provádět v okně Seznam chyb.|-   [Zlepšení kvality kódu pomocí týmového projektu vrácení se změnami zásad](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [Postupy: synchronizace sady pravidel projektu kódu zásadám týmového projektu vrácení se změnami](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [Postupy: vytvoření pracovní položky pro vadu spravovaného kódu](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|