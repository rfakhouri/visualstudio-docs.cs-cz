---
title: Rozhraní refaktoring extrahovat
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: fe61ca799b6df00acc34a0579398d612c142c2c2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028454"
---
# <a name="extract-an-interface-refactoring"></a>Rozhraní refaktoring extrahovat

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje vytvořit rozhraní pomocí stávajících členů ze třídy, struktury nebo rozhraní.

**Kdy:** Máte několik třídy, struktury nebo rozhraní s metodami, které by mohly být provedeny běžné a používá jiné třídy, struktury nebo rozhraní.

**Proč:** Rozhraní jsou skvělé konstrukce pro objektově orientované vzory. Představte si tříd pro různé zvířata (Dog Cat, Bird), které by mohly běžné metody, jako je například Eat nápoje, přejít do režimu spánku. Použití rozhraní jako IAnimal by umožnilo pes, Cat a Bird mají společnou "podpis" pro tyto metody.

## <a name="how-to"></a>Postupy

1. Zvýrazněte název třídy pro akci provést, nebo jenom někam umístit kurzor textu v názvu třídy.

   - C#:

       ![Zvýrazněný kód:C#](media/extractinterface-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/extractinterface-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl + R**, pak **Ctrl + I**. (Všimněte si, že klávesová zkratka může být jiný platformě, na který profil vyberete.)
      - Stisknutím klávesy **Ctrl**+**.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **extrahování rozhraní** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Vyberte **Upravit > Refaktorovat > extrahování rozhraní**.
      - Klikněte pravým tlačítkem na název třídy, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **extrahování rozhraní** z automaticky otevíraného okna okno náhledu.

3. V **extrahování rozhraní** dialogové okno, která se otevře, zadejte informace o dotaz:

   ![extrahování rozhraní](media/extractinterface-dialog-cs.png)


   | Pole | Popis |
   | - | - |
   | **Název nového rozhraní** | Název rozhraní, který se má vytvořit. To bude ve výchozím nastavení můžu*ClassName*, kde *ClassName* je název třídy, které vyberete nahoře. |
   | **Nový název souboru** | Název souboru, který se vygeneruje, která bude obsahovat rozhraní. Jako název rozhraní, to budou ve výchozím nastavení můžu*ClassName*, kde *ClassName* je název třídy, které vyberete nahoře. |
   | **Vybrat veřejné členy rozhraní** | Položky, které chcete extrahovat do rozhraní. Můžete vybrat libovolný počet podle potřeby. |


4. Zvolte **OK**.

   Rozhraní se vytvoří v souboru zadaný název. Kromě toho, kterou jste vybrali třída implementuje rozhraní.

   - C#:

      ![Výsledné třídy – C# ](media/extractinterface-class-cs.png) ![výsledný rozhraní -C#](media/extractinterface-interface-cs.png)

   - Visual Basic:

      ![Výsledné třídy – Visual Basic](media/extractinterface-class-vb.png) ![výsledný rozhraní - jazyka Visual Basic](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)