---
title: Použití sad pravidel k seskupování pravidel analýzy kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: 38
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1da32bd3626af60de56c0a8544753f95988773e9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54759203"
---
# <a name="using-rule-sets-to-group-code-analysis-rules"></a>Použití sad pravidel k seskupování pravidel analýzy kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při konfiguraci analýzy kódu v [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], nebo [!INCLUDE[vsPro](../includes/vspro-md.md)], můžete vybrat ze seznamu Microsoft integrovanou *sad pravidel*. Sada pravidel je logické seskupení pravidel analýzy kódu, která vyhledávají cílené problémy a zvláštní podmínky. Například můžete použít sadu pravidel, která slouží k vyhledání kódu veřejně dostupných rozhraní API, nebo můžete použít sadu pravidel, která obsahuje pouze minimální doporučená pravidla. Můžete také použít sadu pravidel, která zahrnuje všechna pravidla.  
  
 Můžete přizpůsobit sadu přidáním nebo odstraněním pravidel nebo změnou pravidel se zobrazí v pravidel **seznam chyb** okno jako upozornění nebo chyby. Sada vlastních pravidel může splnit potřebu konkrétního vývojového prostředí. Při přizpůsobování sady vlastních pravidel poskytuje stránka sady pravidel nástroje pro vyhledávání a filtrování, které vám s tím pomohou.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Získání praktických postupů:** Použijte nástroje analýzy kódu k určení vlastní sadu pravidel, která Vyhledávejte a opravujte problémy v jednoduché aplikace rozhraní .NET Framework.|-   [Návod: Nastavení konfigurace a používání vlastního pravidla](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**Konfigurace analýzy kódu pro projekt:** Zvolte existující pravidlo pro projekt, webu nebo řešení.|-   [Jak: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [Použití sad pravidel k určování pravidel C++ pro spuštění](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [Jak: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [Jak: Určení sad pravidel pro více projektů v určitém řešení](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**Přizpůsobení sady pravidel:** Zadejte pravidla, která platí pro váš projekt.|-   [Vytváření vlastních sad pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**Principy sad předdefinovaných pravidel:** Zobrazte pravidla analýzy kódu, které tvoří sady předdefinovaných pravidel.|-   [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/code-analysis-rule-set-reference.md)|  
|**Integrace analýzy kódu se serverem Team Foundation Server:** [!INCLUDE[esprtfs](../includes/esprtfs-md.md)] vrácení se změnami zásad umožňují vývojovým týmům Ujistěte se, že všechny kódu vrácení se změnami splňovala veškeré běžné standardy analýzy kódu.|-   [Jak: Synchronizace sad pravidel projektu kódu pomocí zásady vracení se změnami projektu týmu](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|
