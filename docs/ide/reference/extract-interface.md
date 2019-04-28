---
title: Rozhraní refaktoring extrahovat
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 261ddf457ad117812be9971b630c2fcd3b75b550
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62791190"
---
# <a name="extract-an-interface-refactoring"></a>Rozhraní refaktoring extrahovat

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje vytvořit rozhraní pomocí stávajících členů ze třídy, struktury nebo rozhraní.

**Kdy:** Budete mít členové třídy, struktury nebo rozhraní, které by mohly být zděděny jiné třídy, struktury nebo rozhraní.

**Proč:** Rozhraní jsou skvělé konstrukce pro objektově orientované vzory. Představte si tříd pro různé zvířata (Dog Cat, Bird), které by mohly běžné metody, jako je například Eat nápoje, přejít do režimu spánku. Použití rozhraní jako IAnimal by umožnilo pes, Cat a Bird mají společnou "podpis" pro tyto metody.

## <a name="extract-an-interface-refactoring"></a>Rozhraní refaktoring extrahovat

1. Umístěte kurzor na název třídy.

   - C#:

       ![Zvýrazněný kód:C#](media/extractinterface-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/extractinterface-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl + R**, pak **Ctrl + I**. (Klávesová zkratka může lišit na základě profilu, který jste vybrali.)
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **extrahování rozhraní** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Vyberte **Upravit > Refaktorovat > extrahování rozhraní**.
      - Klikněte pravým tlačítkem na název třídy, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **extrahování rozhraní** z automaticky otevíraného okna okno náhledu.

3. V **extrahování rozhraní** dialogové okno, která se otevře, zadejte informace o dotaz:

   ![extrahování rozhraní](media/extractinterface-dialog-same-file.png)

   | Pole | Popis |
   | - | - |
   | **Název nového rozhraní** | Název rozhraní, který se má vytvořit. Název bude ve výchozím nastavení můžu*ClassName*, kde *ClassName* je název třídy, které vyberete nahoře. |
   | **Nový název souboru** | Název generovaného souboru, který bude obsahovat rozhraní. Jak je názvem rozhraní, tento název bude ve výchozím nastavení můžu*ClassName*, kde *ClassName* je název třídy, které vyberete nahoře. Můžete také vybrat možnost **přidat do aktuálního souboru**. |
   | **Vybrat veřejné členy rozhraní** | Položky, které chcete extrahovat do rozhraní. Můžete vybrat libovolný počet podle potřeby. |

4. Zvolte **OK**.

   Rozhraní se vytvoří v souboru zadaný název. Kromě toho, kterou jste vybrali třída implementuje rozhraní.

   - C#:

      ![Výsledné třídy –C#](media/extractinterface-class-cs.png)

      ![Výsledný rozhraní-C#](media/extractinterface-interface-cs.png)

   - Visual Basic:

      ![Výsledné třídy – Visual Basic](media/extractinterface-class-vb.png)

      ![Výsledný rozhraní - jazyka Visual Basic](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Tipy pro vývojáře .NET](../../ide/visual-studio-2017-for-dotnet-developers.md)
