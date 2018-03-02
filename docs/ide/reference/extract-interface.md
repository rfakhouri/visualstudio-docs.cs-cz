---
title: "Extrahování rozhraní refaktoring se v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: e735b194da008de83fddac564194f8bb008c66bb
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="extract-an-interface-refactoring"></a>Extrahování refaktoring rozhraní

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje vytvářet rozhraní pomocí stávající členy z třída, struktura nebo rozhraní.

**Kdy:** máte několik tříd, struktur nebo rozhraní s metody, které se může provést běžné a použít jiné třídy, struktury nebo rozhraní.

**Důvod:** rozhraní jsou skvělý konstrukce pro objektově orientované návrhy. Představte si s třídy pro různé zvířat (PSA Cat, ptačí perspektivy), která může mít běžné metody, jako je například Eat nápoj, přejít do režimu spánku. Pomocí rozhraní jako IAnimal by umožnilo PSA Cat a ptačí perspektivy tak, aby měl běžné "podpis" pro tyto metody.

## <a name="how-to"></a>Postupy

1. Zvýrazněte název třídy provést akci na nebo umístěte kurzor text právě někde v názvu třídy.

   - C#:

    ![Zvýrazněný - C#](media/extractinterface-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/extractinterface-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl + R**, pak **Ctrl + I**. (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **extrahování rozhraní** z okna náhledu – místní nabídka.
   - **Myš**
     - Vyberte **Upravit > Refaktorovat > extrahování rozhraní**.
     - Klikněte pravým tlačítkem na název třídy, vyberte **rychlé akce a refaktoring** nabídku a vyberte **extrahování rozhraní** z okna náhledu – místní nabídka.

1. V **extrahování rozhraní** dialogu, který se zobrazí, zadejte informace o výzva:

   ![extrahování rozhraní](media/extractinterface-dialog-cs.png)

   | Pole | Popis |
   | --- | --- |
   | **Nový název rozhraní** | Název rozhraní, který se má vytvořit. To bude použita výchozí I*ClassName*, kde *ClassName* je název třídy, které jste vybrali výše. |
   | **Nový název souboru** | Název souboru, který se budou generovat a která bude obsahovat rozhraní. Jako s názvem rozhraní to bude použita výchozí I*ClassName*, kde *ClassName* je název třídy, které jste vybrali výše. |
   | **Vyberte veřejné členy do formuláře rozhraní** | Položky k extrakci do rozhraní. Můžete vybrat libovolný počet. Chcete. |

1. Zvolte **OK**.

   Rozhraní je vytvořen v souboru zadaným názvem. Kromě toho implementuje třídy, na kterou jste vybrali tohoto rozhraní.

   - C#:

    ![Výsledné třídy - C#](media/extractinterface-class-cs.png)
    ![výsledné rozhraní - C#](media/extractinterface-interface-cs.png)

   - Visual Basic:

    ![Výsledná třída - jazyka Visual Basic](media/extractinterface-class-vb.png)
    ![výsledné rozhraní - jazyka Visual Basic](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)