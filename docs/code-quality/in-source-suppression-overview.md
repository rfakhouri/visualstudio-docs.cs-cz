---
title: Potlačení upozornění analýzy kódu v sadě Visual Studio | Microsoft Docs
ms.date: 01/29/2018
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: ef69462dc9b51fbd92da11bc5adb1bfa61e8a792
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="suppress-code-analysis-warnings"></a>Potlačení upozornění analýzy kódu

Je často užitečné k označení, že upozornění se nevztahuje. To znamená členům týmu, zda kód je zkontrolovat, a zda lze potlačit upozornění. Zdroj potlačení (ISS) používá <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut k potlačení upozornění. Atribut se může blízko segment kódu, který vygeneroval upozornění. Můžete přidat <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut ke zdrojovému souboru zadáním, nebo můžete použít na upozornění v místní nabídce **seznam chyb** automatické přidání.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> Atribut je podmíněný atribut, který je součástí IL metadata sestavení spravovaného kódu, jenom když je symbol kompilace CODE_ANALYSIS definované při kompilaci.

V jazyce C + +/ CLI, použijte makra certifikační Autority\_POTLAČIT\_zpráva nebo certifikační Autority\_globální\_SUPPRESS_MESSAGE v záhlaví souboru přidat atribut.

> [!NOTE]
> -Source suppressions byste neměli používat u sestavení pro vydání, aby se zabránilo omylem přesouvání metadata potlačení v zdroje. Kromě toho kvůli zpracování náklady potlačení ve zdroje, aplikace může být ke snížení výkonu.

> [!NOTE]
> Pokud provádíte migraci projektu pro Visual Studio 2017, může vám najednou potýkají s čtenáře počet upozornění analýzy kódu. Pokud jste ještě nejsou připraveny upozornění, a chcete dočasně vypnout analýza kódu, otevřete stránky vlastností projektu (**projektu** > ***projektu* vlastnosti...** ) a přejděte na **analýza kódu** kartě. Zrušte výběr **povolit analýza kódu v sestavení**a pak znovu sestavte projekt. Alternativně můžete vybrat jiný, menší sadu pravidel, která spouštění kódu. Mějte na paměti, chcete-li analýza kódu zpět na když budete chtít opravte upozornění.

## <a name="suppressmessage-attribute"></a>SuppressMessage – atribut

Pokud vyberete **potlačit** z nabídky upozornění analýzy kódu v kontextu nebo klikněte pravým tlačítkem **seznam chyb**, <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut se přidá do vašeho kódu nebo do globální potlačení projektu soubor.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> Atribut má následující formát:

```vb
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>
```

```csharp
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]
```

```cpp
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")
```

Vlastnosti atributu:

- **Pravidlo kategorie** – kategorie, ve kterém je definovaný pravidlo. Další informace o kategorií pravidel analýzy kódu najdete v tématu [spravované upozornění kódu](../code-quality/code-analysis-for-managed-code-warnings.md).

- **Pravidlo Id** -identifikátor pravidla. Podpora zahrnuje jak krátký a dlouhý název identifikátor pravidla. Krátký název je CAXXXX; dlouhý název je CAXXXX:FriendlyTypeName.

- **Při zarovnání do bloku** – text, který se používá k dokumentu z důvodu pro potlačení zprávy.

- **Id zprávy** – jedinečný identifikátor problém pro každou zprávu.

- **Obor** -cíl, na kterém je potlačeno upozornění. Pokud není zadaný cíl, je nastaven k cílovému atributu. Podporované obory zahrnují následující:

    - Modul

    - Obor názvů

    - Prostředek

    - Typ

    - Člen

- **Cíl** – identifikátor, který slouží k určení cíle, na kterém je potlačeno upozornění. Musí obsahovat položky plně kvalifikovaný název.

## <a name="suppressmessage-usage"></a>Suppressmessage – použití

Upozornění analýzy kódu jsou potlačovány na úrovni, do kterého <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut se používá. Můžete například použít atribut na sestavení, modulu, typu, člen a úroveň parametr. Účelem tohoto objektu je úzce spojte potlačení informací pomocí kódu kde dojde k porušení zásady.

Obecná forma potlačení zahrnuje kategorie pravidel a identifikátor pravidla, která obsahuje volitelné čitelná pro člověka reprezentace název pravidla. Příklad:

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

Pokud existují striktní výkonu důvody pro minimalizaci metadata potlačení v zdroje, můžete vynechat název pravidla. Kategorie pravidel a jeho ID pravidla společně tvoří pravidlo dostatečně jedinečný identifikátor. Příklad:

`[SuppressMessage("Microsoft.Design", "CA1039")]`

Z důvodů udržovatelnosti vynechání název pravidla se nedoporučuje.

## <a name="suppress-selective-violations-within-a-method-body"></a>Potlačit selektivní porušení v textu – metoda

Potlačení atributů může být použitý na metodu, ale nelze vložit do těla metody. To znamená, že jsou všechny porušení konkrétní pravidlo potlačovány Pokud přidáte <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut do metody.

V některých případech můžete chtít potlačit konkrétní instanci porušení zásady, třeba tak, aby budoucí kód není automaticky vyloučení z pravidel nástroje Analýza kódu. Určitých pravidel analýzy kódu umožňují to provést pomocí `MessageId` vlastnost <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut. Obecně platí, starší pravidel pro porušení na konkrétní symbol (místní proměnné nebo parametru) ohledem `MessageId` vlastnost. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md) je příkladem takové pravidlo. Ale starší verze pravidla pro porušení na spustitelného kódu (bez symbol) neodpovídají `MessageId` vlastnost. Kromě toho nerespektují analyzátorů kompilátoru platformu .NET ("Roslyn") `MessageId` vlastnost.

K potlačení konkrétní symbol porušení pravidel, zadejte název symbolu `MessageId` vlastnost <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut. Následující příklad ukazuje kód, který představuje dva porušení [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;za `name` proměnné a jeden pro `age` proměnné. Pouze porušení pro `age` potlačeno symbol.

```vb
Public Class Animal
    Dim age As Integer
    Dim name As String

    <CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId:="age")>
    Sub PrintInfo()
        Dim age As Integer = 5
        Dim name As String = "Charlie"

        Console.WriteLine("Age {0}, Name {1}", age, name)
    End Sub

End Class
```

```csharp
public class Animal
{
    int age;
    string name;

    [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId = "age")]
    private void PrintInfo()
    {
        int age = 5;
        string name = "Charlie";

        Console.WriteLine($"Age {age}, Name {name}");
    }
}
```

## <a name="generated-code"></a>Generovaný kód

Kompilátory spravovaného kódu a některé nástroje třetích stran pro generování kódu usnadňuje vývoj rychlé kódu. Generované kompilátorem kód, který se zobrazí ve zdrojových souborech obvykle označena `GeneratedCodeAttribute` atribut.

Můžete zvolit, jestli se má potlačit upozornění analýzy kódu a chyby pro vygenerovaný kód. Informace o tom, jak potlačit takové upozornění a chyby najdete v tématu [postupy: potlačení upozornění pro kód generované](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md).

> [!NOTE]
> Analýza kódu ignoruje `GeneratedCodeAttribute` kdy byl použit k celé sestavení nebo jeden parametr.

## <a name="global-level-suppressions"></a>Globální úrovni suppressions

Nástroj Analýza spravovaného kódu zjistí, zda `SuppressMessage` atributy, které se použijí na úrovni sestavení, modulu, typu, člen nebo parametr. Aktivuje se také porušení proti prostředky a obory názvů. Tato porušení se musí použít na globální úrovni a jsou obor a cílem. Například následující zpráva potlačí narušení obor názvů:

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> Když je potlačit upozornění s oborem názvů, potlačí upozornění na obor názvů sám sebe. Je nepotlačuje upozornění s typy v rámci oboru názvů.

Všechny potlačení může být vyjádřený zadáním výslovného oboru. Tyto suppressions musí za provozu na globální úrovni. Potlačení úrovni člena nelze zadat pomocí architekturu typu.

Globální úrovni suppressions jsou jedině k potlačení zprávy, které odkazují na generované kompilátorem kódu, které nejsou namapované do zdroje explicitně zadaný uživatel. Následující kód například potlačí narušení proti konstruktor vygenerované kompilátoru:

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` vždy obsahuje položku plně kvalifikovaný název.

## <a name="global-suppression-file"></a>Globální potlačení souboru

Soubor globální potlačení udržuje suppressions, které jsou globální úrovni suppressions nebo suppressions, které neurčují cíl. Například suppressions pro porušení úrovně sestavení jsou uloženy v tomto souboru. Navíc některé suppressions ASP.NET jsou uloženy v tomto souboru, protože nastavení projektu nejsou k dispozici pro kódu na pozadí formuláře. Globální potlačení soubor je vytvořen a přidán do projektu při prvním vyberete **v souboru projektu potlačení** možnost **potlačit** v příkazu **seznam chyb**okno.

## <a name="see-also"></a>Viz také

- <xref:System.Diagnostics.CodeAnalysis>
- [Použití Roslyn analyzátory](../code-quality/use-roslyn-analyzers.md)