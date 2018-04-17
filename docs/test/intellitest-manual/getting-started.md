---
title: Vytváření testů jednotek zástupných procedur metoda pomocí příkazu Vytvořit testování částí | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Get started
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b87796cd0534129170931c3a527b38ac176bd300
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-microsoft-intellitest"></a>Začínáme s Microsoft IntelliTest

* Pokud je poprvé s IntelliTest:
  * sledování [video Channel 9](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Intellitest)
  * Přečtěte si to [přehled Časopis MSDN](https://msdn.microsoft.com/magazine/dn904672.aspx)
  * Přečtěte si naše [dokumentace](../../test/generate-unit-tests-for-your-code-with-intellitest.md)
* Vaše dotazy posílejte na [Stack Overflow](http://stackoverflow.com/questions/tagged/intellitest)
* Číst zbývající části této příručky odkaz
* Vytiskněte si tuto stránku Stručná referenční příručka

## <a name="important-attributes"></a>Důležité atributy

* [PexClass](attribute-glossary.md#pexclass) označuje typ obsahující **PUT**
* [PexMethod](attribute-glossary.md#pexmethod) značky **PUT**
* [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull) označí parametr nesmí být nulová

```csharp
using Microsoft.Pex.Framework;

[..., PexClass(typeof(Foo))]
public partial class FooTest {
    [PexMethod]
    public void Bar([PexAssumeNotNull]Foo target, int i) {
        target.Bar(i);
    }
}
```

* [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest) váže testovacího projektu do projektu
* [PexInstrumentAssembly](attribute-glossary.md#pexinstrumentassemblyattribute) určuje sestavení účelem instrumentace

```csharp
[assembly: PexAssemblyUnderTest("MyAssembly")] // also instruments "MyAssembly"
[assembly: PexInstrumentAssembly("Lib")]
```

## <a name="helper-classes"></a> Důležité statické pomocné třídy

* [PexAssume](static-helper-classes.md#pexassume) vyhodnotí předpoklady (vstupní filtrování)
* [PexAssert](static-helper-classes.md#pexassert) vyhodnotí kontrolní výrazy
* [PexChoose](static-helper-classes.md#pexchoose) vygeneruje nové možnosti (další vstupy)
* [PexObserve](static-helper-classes.md#pexobserve) protokoly za provozu hodnoty do vygenerované testů

```csharp
[PexMethod]
void StaticHelpers(Foo target) {
    PexAssume.IsNotNull(target);

    int i = PexChoose.Value<int>("i");
    string result = target.Bar(i);

    PexObserve.ValueForViewing<string>("result", result);
    PexAssert.IsNotNull(result);
}
```

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest).
