---
title: Převedení metody Get na vlastnost a převod vlastnosti na metodu Get
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
ms.devlang: csharp
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 0af901ed6a51b962b7b2999b04909136bbb0f3e9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53861144"
---
# <a name="convert-get-method-to-property--convert-property-to-get-method-refactorings"></a>Převedení metody Get na vlastnost / vlastnost převést na refaktoringy Get – metoda

Tyto refaktoringy platí pro:

- C#

## <a name="convert-get-method-to-property"></a>Převedení metody Get na vlastnost

**Co:** Umožňuje převést metody Get na vlastnosti (a volitelně metodu Set).

**Kdy:** Máte metodu Get, který neobsahuje žádnou logiku.

### <a name="how-to"></a>Postupy

1. Umístěte ukazatel myši v názvu metody Get.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **nahraďte metodu pomocí vlastnosti** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **nahraďte metodu vlastnost** z automaticky otevíraného okna okno náhledu.

1. (Volitelné) Pokud máte metodu Set, můžete také metodu Set v tuto chvíli převést tak, že vyberete **metoda nahradit Get a Set – metoda s vlastností**.

1. Pokud jste spokojení se změnou ve verzi preview kód, stiskněte **Enter** nebo klikněte na opravu z nabídky a změny budou potvrzeny.

Příklad:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>Převod vlastnosti na metodu Get

**Co:** Umožňuje převod vlastnosti na metodu Get

**Kdy:** Má-li vlastnost, která zahrnuje více než okamžitě nastavení a získání hodnoty

### <a name="how-to"></a>Postupy

1. Umístěte ukazatel myši v názvu metody Get.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **vlastnost nahraďte metody** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **vlastnost nahraďte metody** z automaticky otevíraného okna okno náhledu.

1. Pokud jste spokojení se změnou ve verzi preview kód, stiskněte **Enter** nebo klikněte na opravu z nabídky a změny budou potvrzeny.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)