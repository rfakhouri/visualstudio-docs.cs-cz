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
ms.assetid: 21FE4D68-9E7F-4BB1-BD69-B0D09A941F09
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: e89b6d8860e0964eacb9d58f6d92c64cc661afa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="get-started-with-microsoft-intellitest"></a>Začínáme s Microsoft IntelliTest

* Pokud je poprvé s IntelliTest:
  * sledování [video Channel 9](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Intellitest)
  * Přečtěte si to [přehled Časopis MSDN](https://msdn.microsoft.com/magazine/dn904672.aspx)
  * Přečtěte si naše [dokumentace](https://docs.microsoft.com/en-gb/visualstudio/test/generate-unit-tests-for-your-code-with-intellitest)
* Vaše dotazy posílejte na [stackoverflow](http://stackoverflow.com/questions/tagged/intellitest)
* Číst zbývající části této příručky odkaz
* Vytiskněte si tuto stránku Stručná referenční příručka

<a name="important-attributes"></a>
## <a name="important-attributes"></a>Důležité atributy

* [PexClass](attribute-glossary.md#pexclass) označuje typ obsahující **PUT**
* [PexMethod](attribute-glossary.md#pexmethod) značky **PUT**
* [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull) označí parametr nesmí být nulová 

```
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

```
[assembly: PexAssemblyUnderTest("MyAssembly")] // also instruments "MyAssembly"
[assembly: PexInstrumentAssembly("Lib")]
```

<a name="helper-classes"></a>
## <a name="important-static-helper-classes"></a>Důležité statické pomocné třídy

* [PexAssume](static-helper-classes.md#pexassume) vyhodnotí předpoklady (vstupní filtrování)
* [PexAssert](static-helper-classes.md#pexassert) vyhodnotí kontrolní výrazy
* [PexChoose](static-helper-classes.md#pexchoose) vygeneruje nové možnosti (další vstupy)
* [PexObserve](static-helper-classes.md#pexobserve) protokoly za provozu hodnoty do vygenerované testů

```
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

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
