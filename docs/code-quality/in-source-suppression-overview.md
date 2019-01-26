---
title: Potlačení upozornění analýzy kódu
ms.date: 12/01/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 7fd2d8323a249771357ca0b32dc3106f11d8aa1b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036183"
---
# <a name="suppress-code-analysis-warnings"></a>Potlačení upozornění analýzy kódu

Často je užitečné k označení, že varování není použitelné. To znamená pro členy týmu, který byl recenzován kód a, který lze potlačit upozornění. Zdroj potlačení (ISS) používá <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut upozornění můžete potlačit. Atribut mohou být umístěny blízko segmentu kódu, které upozornění vygenerovalo. Můžete přidat <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut ke zdrojovému souboru tak, že zadáte v, nebo můžete použít na upozornění v místní nabídce **seznam chyb** a přidejte ji automaticky.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> Atribut je podmíněný atribut, který je součástí metadata IL sestavení spravovaného kódu, pouze v případě, že je definován symbol kompilace CODE_ANALYSIS v době kompilace.

V jazyce C + +/ CLI, použijte makra certifikační Autority\_POTLAČIT\_zprávy nebo certifikační Autorita\_globální\_SUPPRESS_MESSAGE v hlavičkovém souboru při přidání atributu.

> [!NOTE]
> Potlačení v zdroj byste neměli používat u sestavení pro vydání, aby se zabránilo omylem přesouvání potlačení v zdroje metadat. Navíc vzhledem k zpracování potlačení-source, může být snížený výkon vaší aplikace.

> [!NOTE]
> Pokud provádíte migraci projekt do sady Visual Studio 2017, může vás prudce potýkají s velký počet upozornění analýzy kódu. Tato upozornění pocházejí z [analyzátory Roslyn](roslyn-analyzers-overview.md). Pokud vám ještě nejsou připravené k vyřešení upozornění, můžete je všechny potlačit výběrem **analyzovat** > **spustit analýzu kódu a potlačit aktivních problémů**.
>
> ![Spustit analýzu kódu a potlačit problémy v sadě Visual Studio](media/suppress-active-issues.png)

## <a name="suppressmessage-attribute"></a>SuppressMessage – atribut

Při výběru **potlačit** z nabídky upozornění analýzy kódu v kontextu nebo klikněte pravým tlačítkem **seznam chyb**, <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> je ve vašem kódu nebo globální potlačení projektu přidat atribut soubor.

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

- **Kategorie** – kategorie, ve které je definováno pravidlo. Další informace o kategoriích pravidla analýzy kódu, naleznete v tématu [spravovat upozornění kódu](../code-quality/code-analysis-for-managed-code-warnings.md).

- **ID kontroly** -identifikátor pravidla. Podpora zahrnuje jak krátký a dlouhý název identifikátor pravidla. Krátký název je CAXXXX; dlouhý název je CAXXXX:FriendlyTypeName.

- **Odůvodnění** – text, který se používá k dokumentu důvod pro potlačení zprávy.

- **ID zprávy** – jedinečný identifikátor pro každou zprávu problém.

- **Obor** – cíl, na kterém je potlačeno upozornění. Pokud cíl není zadán, je nastavena na cíl atributu. Podporované [obory](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) patří následující:

   - `module`

   - `resource`

   - `type`

   - `member`

   - `namespace` – Tento obor potlačí upozornění pro obor názvů, samotného. Upozornění s typy v rámci oboru názvů je nepotlačuje.

   - `namespaceanddescendants` – Tento obor (Nový pro Visual Studio 2019) potlačí upozornění v oboru názvů a všechny jeho odvozené symboly. `namespaceanddescendants` Hodnota je platná pouze pro analyzátory Roslyn a je ignorován binární, na základě FxCop statické analýzy.

- **Cíl** – identifikátor, který se používá k určení cíle, na kterém je potlačeno upozornění. Musí obsahovat položky plně kvalifikovaný název.

## <a name="suppressmessage-usage"></a>SuppressMessage využití

Upozornění analýzy kódu jsou potlačeny na úrovni, do kterého <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut se používá. Například atribut lze použít v sestavení, modulu, typu, člen nebo parametr úroveň. Účelem tohoto objektu je úzce spárovat informace o potlačení kódu kde dojde k porušení zásady.

Obecný tvar potlačení obsahuje kategorie pravidel a identifikátor pravidla, která obsahuje reprezentaci volitelné čitelný název pravidla. Příklad:

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

Pokud jsou kvůli výkonu přísné pro minimalizaci potlačení v zdroje metadat, můžete vynechat název pravidla. Kategorie pravidel a jeho ID pravidla společně tvoří pravidlo dostatečně jedinečný identifikátor. Příklad:

`[SuppressMessage("Microsoft.Design", "CA1039")]`

Z důvodu udržovatelnosti vynechání název pravidla se nedoporučuje.

## <a name="suppress-selective-violations-within-a-method-body"></a>Potlačit selektivní narušení v těle metody

Potlačení atributy lze použít pro metodu, ale nemůže být vložený, v těle metody. To znamená, že jsou potlačeny porušování je konkrétní pravidlo, pokud chcete přidat <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut do metody.

V některých případech můžete chtít potlačit konkrétní instanci porušení zásady, třeba tak, že budoucí kód není automaticky vyloučit z pravidel nástroje Analýza kódu. Určitá pravidla analýzy kódu bylo možné provést pomocí `MessageId` vlastnost <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut. Obecně platí, starší verze pravidla pro porušení na konkrétním symbolem (lokální proměnná ani parametr) dodržování `MessageId` vlastnost. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md) je příkladem takové pravidlo. Nicméně, nerespektují starší pravidla pro porušení na spustitelný kód (bez symbolů) `MessageId` vlastnost. Kromě toho, nerespektují analyzátory .NET Compiler Platform ("Roslyn") `MessageId` vlastnost.

Potlačit konkrétní symbol porušení pravidla, zadejte název symbolu `MessageId` vlastnost <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atribut. Následující příklad ukazuje kód pomocí dvou porušení [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;jeden pro `name` proměnné a jeden pro `age` proměnné. Pouze porušení pro `age` symbol je potlačeno.

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

Spravovaný kód kompilátory a některé nástroje třetích stran generování kódu pro usnadnění vývoje rychlý kód. Kód generovaný kompilátorem, který se zobrazí ve zdrojových souborech obvykle označené `GeneratedCodeAttribute` atribut.

Můžete zvolit, jestli se má potlačit upozornění analýzy kódu a chyby pro vygenerovaný kód. Informace o tom, jak potlačit takové upozornění a chyby najdete v tématu [jak: Potlačení upozornění pro vygenerovaný kód](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md).

> [!NOTE]
> Analýza kódu ignoruje `GeneratedCodeAttribute` při použití na celé sestavení nebo jeden parametr.

## <a name="global-level-suppressions"></a>Potlačení na globální úrovni

Nástroj pro analýzu spravovaného kódu prozkoumá `SuppressMessage` atributy, které jsou použity na úrovni sestavení, modulu, typu, člen nebo parametr. Je také vyvoláno porušení proti prostředky a obory názvů. Tato porušení se musí použít na globální úrovni a jsou obor a cílem. Například následující zpráva potlačí narušení obor názvů:

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> Kdy potlačit upozornění se `namespace` oboru, potlačí upozornění pro obor názvů, samotného. Upozornění s typy v rámci oboru názvů je nepotlačuje.

Žádné potlačení lze vyjádřit zadáním výslovného oboru. Tyto potlačení musí být aktivní na globální úrovni. Potlačení na úrovni člena nelze zadat pomocí upravení typu.

Potlačení na globální úrovni jsou jediným způsobem, jak potlačí zobrazování zpráv, které odkazují na kód generovaný kompilátorem, které nejsou namapované na výslovně zadaný uživatelský zdroj. Například následující kód potlačí porušení proti vyslaném kompilátor konstruktor:

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` vždy obsahuje plně kvalifikovaný název.

## <a name="global-suppression-file"></a>Soubor globálního potlačení

Soubor globálního potlačení udržuje potlačení, které jsou potlačení na globální úrovni nebo potlačení, u kterých není cíl. Například pro porušení úrovně sestavení jsou uložena v tomto souboru. Kromě toho některé technologie ASP.NET jsou uložena v tomto souboru vzhledem k tomu, že nastavení na úrovni projektu nejsou k dispozici pro kódu na pozadí formuláře. Soubor globálního potlačení je vytvořen a přidán do projektu poprvé, kterou jste vybrali **v souboru potlačení projektu** možnost **potlačit** v příkaz **seznam chyb**okna.

## <a name="see-also"></a>Viz také:

- <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope>
- <xref:System.Diagnostics.CodeAnalysis>
- [Používání analyzátorů Roslyn](../code-quality/use-roslyn-analyzers.md)