---
title: "Extrahování rozhraní - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: db857fb1-3e22-46e2-b15a-56ef9f329235
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractinterface
dev_langs: VB
ms.openlocfilehash: 9616cae1282b992722f75eee091e2c9d271e85f6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extract-an-interface-in-visual-basic"></a>Extrahování rozhraní v jazyce Visual Basic
**Co:** umožňuje vytvářet rozhraní pomocí stávající členy z třída, struktura nebo rozhraní.

**Kdy:** máte několik tříd, struktur nebo rozhraní s metody, které se může provést běžné a použít jiné třídy, struktury nebo rozhraní.

**Důvod:** rozhraní jsou skvělý konstrukce pro objektově orientované návrhy.  Představte si s třídy pro různé zvířat (PSA Cat, ptačí perspektivy), která může mít běžné metody, jako je například Eat nápoj, přejít do režimu spánku.  Pomocí rozhraní jako IAnimal by umožnilo PSA Cat a ptačí perspektivy tak, aby měl běžné "podpis" pro tyto metody.  

**Postupy:**

1. Zvýrazněte název třídy provést akci na nebo umístěte kurzor text právě někde v názvu třídy.

   ![Zvýrazněný kód](media/extractinterface_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **Ctrl + I**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **extrahování rozhraní** z okna náhledu – místní nabídka.
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > extrahování rozhraní**.
     * Klikněte pravým tlačítkem na název třídy, vyberte **rychlé akce a refaktoring** nabídku a vyberte **extrahování rozhraní** z okna náhledu – místní nabídka.

1. V **extrahování rozhraní** dialogu, který se zobrazí, zadejte informace o výzva: ![extrahování rozhraní](media/extractinterface_dialog.png)
   | Pole | Popis |
   | --- | --- |
   | **Nový název rozhraní** | Název rozhraní, který se má vytvořit. To bude použita výchozí I*ClassName*, kde *ClassName* je název třídy, které jste vybrali výše. |
   | **Nový název souboru** | Název souboru, který se budou generovat a která bude obsahovat rozhraní. Jako s názvem rozhraní to bude použita výchozí I*ClassName*, kde *ClassName* je název třídy, které jste vybrali výše. |
   | **Vyberte veřejné členy do formuláře rozhraní** | Položky k extrakci do rozhraní.  Můžete vybrat libovolný počet. Chcete. |

1. Click **OK**.

   Rozhraní okamžitě vytvoří se v souboru zadaným názvem.  Třídy, na kterou jste vybrali bude nyní implementovat dané rozhraní.

   ![Výsledná třída](media/extractinterface_class.png)
   ![výsledné rozhraní](media/extractinterface_interface.png)

## <a name="see-also"></a>Viz také
[Refaktoringu (Visual Basic)](../refactoring-vb.md)