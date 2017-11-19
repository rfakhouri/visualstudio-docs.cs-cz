---
title: "Analýza kódu pro spravovaný kód přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
ms.assetid: 12ec0dab-46a4-43d8-984a-440730ef37a9
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: eebc25b344e603cb66546db6d9179067d5995496
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="code-analysis-for-managed-code-overview"></a>Přehled Analýzy kódu pro spravovaný kód
Analýza kódu pro spravovaný kód analyzuje spravovaná sestavení a hlásí informace o sestavení, jako je například porušení programování a pravidla návrhu podle pokynů pro návrh rozhraní Microsoft .NET Framework.  
  
 Nástroj pro analýzu představuje kontroly, které provádí během analýzu jako zprávy upozornění. Zprávy upozornění zjištění problémů relevantní programování a návrhu a kdy je možné, dodávky informace o tom, jak problém opravte.  
  
## <a name="ide-integrated-development-environment-integration"></a>Integrace rozhraní IDE (integrované vývojové prostředí)  
 Jako vývojář analýza kódu v projektu lze spustit automaticky nebo ji můžete spustit ručně.  
  
 Spuštění analýzy kódu pokaždé, když vytváříte projekt, vyberte **povolit analýza kódu v sestavení (definuje CODE_ANALYSIS konstanta)** na stránce vlastností projektu. Další informace najdete v tématu [postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).  
  
 K ruční spuštění analýzy kódu v projektu, na **analyzovat** nabídky, klikněte na tlačítko **spuštění analýzy kódu na***ProjectName*. Další informace najdete v tématu [postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).  
  
## <a name="rule-sets"></a>Sady pravidel  
 Pravidel analýzy kódu pro spravovaný kód jsou seskupené do *sad pravidel*. Můžete použít jednu standardní pravidla sad Microsoft, nebo můžete vytvořit vlastní sadu pravidel, která splnit konkrétní potřebu. Další informace najdete v tématu [pomocí sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md).  
  
## <a name="in-source-suppression"></a>V potlačení zdroje  
 Často je užitečné znamenat, že upozornění nepoužitelné. Tento příkaz informuje na vývojáře a ostatní uživatelé, kteří mohou projít později, že upozornění byla prozkoumat a potlačena nebo ignorovat.  
  
 Potlačení zdroje upozornění se implementuje prostřednictvím vlastních atributů. Potlačit upozornění, přidejte atribut `SuppressMessage` ke zdrojovému kódu, jak je znázorněno v následujícím příkladu:  
  
 `[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 `Public class MyClass`  
  
 `{`  
  
 `// code`  
  
 `}`  
  
 Další informace najdete v tématu [potlačení upozornění s použitím atributu SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md).  
  
## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Spuštění v rámci zásad vrácení se změnami analýzy kódu  
 Organizace můžete vyžadovat, aby všechny vrácení se změnami splňovat určité zásady. Konkrétně je vhodné dodržovat tyto zásady:  
  
-   Nedošlo k chybám sestavení v kódu se změnami.  
  
-   Analýza kódu byla spuštěna jako součást poslední sestavení.  
  
 Toho lze dosáhnout zadáním zásad vrácení se změnami. Další informace najdete v tématu [zlepšení kvality kódu pomocí zásad vrácení se změnami týmového projektu](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).  
  
## <a name="team-build-integration"></a>Integrace sestavení Team  
 Integrované funkce systém sestavení můžete spustit nástroj pro analýzu v rámci procesu sestavení. Další informace najdete v tématu [sestavení aplikace](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
## <a name="see-also"></a>Viz také  
 [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)   
 [Postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)