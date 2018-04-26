---
title: Analýza kódu pro spravovaný kód v sadě Visual Studio
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b7b992dadb703cf1c4f73830324e9934d7525645
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="overview-of-code-analysis-for-managed-code"></a>Přehled analýzy kódu pro spravovaný kód

Visual Studio 2017 analyzuje spravovaného kódu dvěma způsoby: pomocí starší verze *FxCop* statické analýzy spravovaných sestavení a s platformou .NET kompilátoru *analyzátorů*. Toto téma popisuje analýza FxCop statické kódu. Další informace o analýze kódu pomocí analyzátorů kompilátoru platformy .NET najdete v tématu [přehled Roslyn analyzátorů](../code-quality/roslyn-analyzers-overview.md).

Analýza kódu pro spravovaný kód analyzuje spravovaná sestavení a hlásí informace o sestavení, jako je například porušení programování a pravidla návrhu podle pokynů pro návrh rozhraní Microsoft .NET Framework.

Nástroj pro analýzu představuje kontroly, které provádí během analýzu jako zprávy upozornění. Zprávy upozornění zjištění problémů relevantní programování a návrhu a kdy je možné, dodávky informace o tom, jak problém opravte.

## <a name="ide-integrated-development-environment-integration"></a>Integrace rozhraní IDE (integrované vývojové prostředí)

Analýza kódu v projektu můžete spustit ručně nebo automaticky.

Chcete-li spuštění analýzy kódu pokaždé, když vytváříte projekt, vyberte **povolit analýza kódu v sestavení** na stránce vlastností projektu. Další informace najdete v tématu [postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

Ruční spuštění analýzy kódu v projektu, z řádku nabídek zvolte **analyzovat** > **spuštění analýzy kódu** > **spuštění analýzy kódu na \<projektu >**.

## <a name="rule-sets"></a>Sady pravidel

Pravidel analýzy kódu pro spravovaný kód jsou seskupené do [sad pravidel](../code-quality/using-rule-sets-to-group-code-analysis-rules.md). Můžete použít jednu standardní pravidla sad Microsoft, nebo můžete [vytvoření vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md) splnit konkrétní potřebu.

## <a name="suppress-warnings"></a>Potlačení upozornění

Často je užitečné znamenat, že upozornění nepoužitelné. Tento příkaz informuje na vývojáře a ostatní uživatelé, kteří mohou projít později, že upozornění byla prozkoumat a potlačena nebo ignorovat.

Potlačení v zdroje upozornění se implementuje pomocí vlastních atributů. Potlačit upozornění, přidejte atribut `SuppressMessage` ke zdrojovému kódu, jak je znázorněno v následujícím příkladu:

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

Další informace najdete v tématu [potlačení upozornění](../code-quality/in-source-suppression-overview.md).

> [!NOTE]
> Pokud provádíte migraci projektu pro Visual Studio 2017, může vám najednou potýkají s velkým počtem upozornění analýzy kódu. Pokud jste ještě nejsou připraveny upozornění a chtějí být produktivní hned, můžete *směrného plánu* analysis stav projektu. Z **analyzovat** nabídce vyberte možnost **spuštění analýzy kódu a potlačit aktivní problémy**.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Spuštění v rámci zásad vrácení se změnami analýzy kódu

Organizace můžete vyžadovat, aby všechny vrácení se změnami splňovat určité zásady. Konkrétně je vhodné dodržovat tyto zásady:

- Nejsou žádné chyby sestavení v kódu se změnami.

- Analýza kódu je spuštěn jako součást poslední sestavení.

Toho lze dosáhnout zadáním zásad vrácení se změnami. Další informace najdete v tématu [zlepšení kvality kódu pomocí zásad vrácení se změnami týmového projektu](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).

## <a name="team-build-integration"></a>Integrace sestavení Team

Integrované funkce systém sestavení můžete spustit nástroj pro analýzu v rámci procesu sestavení. Další informace najdete v tématu [sestavení a verzí (VSTS)](/vsts/build-release/index).

## <a name="see-also"></a>Viz také

- [Přehled Roslyn analyzátory](../code-quality/roslyn-analyzers-overview.md)
- [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Postupy: povolení a zákaz automatické analýzy kódu](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
