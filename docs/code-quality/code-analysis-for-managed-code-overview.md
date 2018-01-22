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
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 8739c5aafbc8914e3de5f0a51659b40234fa079c
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="code-analysis-for-managed-code-overview"></a>Analýza kódu pro spravovaný kód – přehled

Analýza kódu pro spravovaný kód analyzuje spravovaná sestavení a hlásí informace o sestavení, jako je například porušení programování a pravidla návrhu podle pokynů pro návrh rozhraní Microsoft .NET Framework.

Nástroj pro analýzu představuje kontroly, které provádí během analýzu jako zprávy upozornění. Zprávy upozornění zjištění problémů relevantní programování a návrhu a kdy je možné, dodávky informace o tom, jak problém opravte.

## <a name="ide-integrated-development-environment-integration"></a>Integrace rozhraní IDE (integrované vývojové prostředí)

Analýza kódu v projektu můžete spustit ručně nebo automaticky.

Chcete-li spuštění analýzy kódu pokaždé, když vytváříte projekt, vyberte **povolit analýza kódu v sestavení** na stránce vlastností projektu. Další informace najdete v tématu [postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

Chcete-li ruční spuštění analýzy kódu v projektu, z řádku nabídek zvolte **analyzovat** > **spuštění analýzy kódu** > **spuštění analýzy kódu na <project>** . Další informace najdete v tématu [postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

## <a name="rule-sets"></a>Sady pravidel

Pravidel analýzy kódu pro spravovaný kód jsou seskupené do *sad pravidel*. Můžete použít jednu standardní pravidla sad Microsoft, nebo můžete vytvořit vlastní sadu pravidel, která splnit konkrétní potřebu. Další informace najdete v tématu [pomocí sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md).

## <a name="in-source-suppression"></a>V potlačení zdroje

Často je užitečné znamenat, že upozornění nepoužitelné. Tento příkaz informuje na vývojáře a ostatní uživatelé, kteří mohou projít později, že upozornění byla prozkoumat a potlačena nebo ignorovat.

Ve zdroji je implementována potlačení upozornění prostřednictvím vlastních atributů. Potlačit upozornění, přidejte atribut `SuppressMessage` ke zdrojovému kódu, jak je znázorněno v následujícím příkladu:

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

Další informace najdete v tématu [potlačení upozornění s použitím atributu SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md).

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Spuštění v rámci zásad vrácení se změnami analýzy kódu

Organizace můžete vyžadovat, aby všechny vrácení se změnami splňovat určité zásady. Konkrétně je vhodné dodržovat tyto zásady:

- Nejsou žádné chyby sestavení v kódu se změnami.

- Analýza kódu je spuštěn jako součást poslední sestavení.

Toho lze dosáhnout zadáním zásad vrácení se změnami. Další informace najdete v tématu [zlepšení kvality kódu pomocí zásad vrácení se změnami týmového projektu](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).

## <a name="team-build-integration"></a>Integrace sestavení Team

Integrované funkce systém sestavení můžete spustit nástroj pro analýzu v rámci procesu sestavení. Další informace najdete v tématu [sestavení a verzí (VSTS)](/vsts/build-release/index).

## <a name="see-also"></a>Viz také

[Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)   
[Postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
