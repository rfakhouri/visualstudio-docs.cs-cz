---
title: Přejmenování a přesunutí tříd a typů v Návrháři tříd
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.ClassDesigner.OverrideMembersDialog
helpviewer_keywords:
- members, overriding
- overriding members
- classes [Visual Studio], refactoring
- type members, overriding
- refactoring, types
- types [Visual Studio], refactoring
- Class Designer [Visual Studio], refactoring classes
- refactoring, classes
ms.assetid: dcf07bb4-fa3b-4224-9dec-566fd924a8ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83649a5b2b1053453a36e5ae8ad6f8636112ffd9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069509"
---
# <a name="refactor-classes-and-types-in-class-designer"></a>Refaktoring tříd a typů v Návrháři tříd

Když refaktorujete kód, můžete bylo snazší porozumět, udržovat a efektivnější tak, že změníte její interní strukturu a způsobu jeho objektů navržena, není externí chování. Použijte návrhář tříd a okně podrobností třídy ke snížení práci, kterou musíte udělat a riziko chyb zavádění, když refaktorujete C#, Visual Basic nebo C++ kód v projektu sady Visual Studio.

> [!NOTE]
> Soubory projektu může být jen pro čtení, protože projekt je pod správou zdrojového kódu a není rezervován, jedná o Odkazovaný projekt, nebo jeho soubory označené jako jen pro čtení na disku. Při práci v projektu v jednom z těchto stavů, zobrazí se různé způsoby, jak uložit práci v závislosti na stavu projektu. To platí pro refaktoring kódu a také na kód, který změníte jiným způsobem, jako je například Přímá úprava.

## <a name="common-tasks"></a>Běžné úkoly

|Úloha|Podpůrný obsah|
|----------| - |
|**Refaktoring tříd:** Operace refaktoringu můžete použít k rozdělení třídy na částečné třídy nebo k implementaci abstraktní základní třídu.|-   [Jak: Rozdělení třídy na částečné třídy](how-to-split-a-class-into-partial-classes.md)|
|**Práce s rozhraní:** V Návrháři tříd můžete implementovat rozhraní v diagramu tříd díky připojení k třídu, která poskytuje kód pro metody rozhraní.|-   [Jak: Implementovat rozhraní](how-to-implement-an-interface.md)|
|**Refaktoring parametry, typy a členy typu:** Pomocí návrháře tříd můžete přejmenovat typy, přepsat členy typu nebo je přesunout z jednoho typu na jiný. Můžete také vytvořit typy připouštějící hodnotu Null.|-   [Přejmenování typů a členů typu](#rename-types-and-type-members)<br />-   [Členy typu přesuňte z jednoho typu na jiný](#move-type-members-from-one-type-to-another)<br />-   [Jak: Vytvoření typu s možnou hodnotou Null](how-to-create-a-nullable-type.md)|

## <a name="rename-types-and-type-members"></a>Přejmenování typů a členů typu

V Návrháři tříd můžete přejmenovat typ nebo člen typu v diagramu tříd nebo v **vlastnosti** okna. V **podrobností třídy** okna, můžete změnit název člena, ale není typu. Přejmenování typ nebo člen typu rozšíří pro všechna okna a kódem umístění, kde se nacházela původní název.

### <a name="rename-in-the-class-designer"></a>Přejmenovat v Návrháři tříd

1. V diagramu tříd vyberte typ nebo člena a vyberte název.

     Název členu bude možné editovat.

2. Zadejte nový název pro tento typ nebo člen typu

### <a name="rename-in-the-class-details-window"></a>Přejmenovat v okně podrobností třídy

1. Chcete-li zobrazit **podrobností třídy** okna, klikněte pravým tlačítkem na typ nebo člen typu a vyberte **podrobností třídy**.

     **Podrobností třídy** zobrazí se okno.

2. V **název** sloupce, změňte název členu typu

3. Chcete-li přesunout fokus z buňky, stiskněte **Enter** klíče nebo klikněte na tlačítko mimo buňku.

    > [!NOTE]
    > V **podrobností třídy** okna, můžete změnit název člena, ale není typu.

### <a name="rename-in-the-properties-window"></a>Přejmenovat v okně Vlastnosti

1. V diagramu tříd nebo **podrobností třídy** okna, klikněte pravým tlačítkem na tento typ nebo člen a pak vyberte **vlastnosti**.

     **Vlastnosti** okno se zobrazí a zobrazí se vlastnosti pro tento typ nebo člen typu.

2. V **název** vlastnosti, změňte název typu nebo typ člena.

     Nový název šíří pro všechna okna a umístění kódu v aktuálním projektu, kde se nacházela původní název.

## <a name="move-type-members-from-one-type-to-another"></a>Členy typu přesuňte z jednoho typu na jiný

Pomocí **návrhář tříd**, člen typu můžete přesunout z jednoho typu na jiný typ. Oba typy musí být viditelné v aktuálním diagramu tříd.

1. V typu, který je viditelný na návrhové ploše, klikněte pravým tlačítkem na člena, kterou chcete přesunout na jiný typ a pak vyberte **Vyjmout**.

2. Klikněte pravým tlačítkem na typ cíle a vyberte **vložit**.

     Vlastnost se odebere z typ zdroje a zobrazí se v cílovém typu.

## <a name="see-also"></a>Viz také:

- [Navrhování tříd a typů](designing-and-viewing-classes-and-types.md)