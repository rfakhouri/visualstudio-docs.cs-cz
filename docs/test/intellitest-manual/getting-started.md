---
title: "Vytváření testů jednotek zástupných procedur metoda pomocí příkazu Vytvořit testování částí | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Get started
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 9016006f9774c4a9eff2937f32543b9f8d9f5fb8
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
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

## <a name="helper-classes"></a>Důležité statické pomocné třídy

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
