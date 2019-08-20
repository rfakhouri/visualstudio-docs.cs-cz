---
title: Návrh model Windows Formsch aplikací
ms.date: 08/09/2019
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms Designer
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0df8b7ec5955f472d716af2850d2ab0b776c6552
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2019
ms.locfileid: "69585329"
---
# <a name="windows-forms-designer-overview"></a>Přehled nástroje Návrhář formulářů

Návrhář formulářů v aplikaci Visual Studio poskytuje rychlé vývojové řešení pro vytváření aplikací založených na model Windows Forms. Návrhář formulářů umožňuje snadno přidat ovládací prvky do formuláře, uspořádat je a napsat kód pro své události. Další informace o model Windows Forms najdete v tématu [model Windows Forms Overview](/dotnet/framework/winforms/windows-forms-overview).

## <a name="functionality"></a>Funkce

Pomocí návrháře můžete:

- Do formuláře přidejte součásti, ovládací prvky pro data nebo ovládací prvky založené na systému Windows.

- Dvakrát klikněte na formulář v návrháři a napište kód v `Load` události pro tento formulář, nebo dvakrát klikněte na ovládací prvek ve formuláři a napište kód pro výchozí událost ovládacího prvku.

- Upravte vlastnost text ovládacího prvku tak, že vyberete ovládací prvek a zadáte název.

- Umístění vybraného ovládacího prvku upravíte přesunutím pomocí myši nebo kláves se šipkami. Podobně upravte umístění přesněji pomocí kláves CTRL a šipky. Nakonec upravte velikost ovládacího prvku pomocí kláves SHIFT a šipky.

- Vyberte více ovládacích prvků tak, že při kliknutí na tlačítko **SHIFT** nebo **CTRL** vyberete možnost. Při použití jednotlivě **SHIFT**+ Click je prvním vybraným ovládacím prvkem dominantní ovládací prvek při zarovnání nebo manipulaci s velikostí. Při použití **kombinace kláves CTRL**+ kliknutí je poslední vybraný ovládací prvek dominantní, takže dominantní ovládací prvek se změní při každém přidání nového ovládacího prvku. Alternativně můžete vybrat více ovládacích prvků přetažením obdélníku výběru kolem ovládacích prvků, které chcete vybrat.

> [!NOTE]
> K provedení změn v souboru prostředků formuláře ( *. resx*) použijte Návrhář formulářů, a ne editor prostředků. Pokud upravujete soubor. resx založený na formuláři, může se zobrazit upozornění, že změny, které provedete v editoru prostředků, mohou být ztraceny. Důvodem je, že Návrhář formulářů generuje soubor. resx.

## <a name="see-also"></a>Viz také:

- [Přehled model Windows Forms](/dotnet/framework/winforms/windows-forms-overview)
- [Ovládací prvky model Windows Forms](/dotnet/framework/winforms/controls/)
- [Vstup uživatele v model Windows Forms](/dotnet/framework/winforms/user-input-in-windows-forms)
- [Datová vazba v model Windows Forms](/dotnet/framework/winforms/windows-forms-data-binding)
- [Vylepšení model Windows Formsch aplikací](/dotnet/framework/winforms/advanced/)
- <xref:System.Windows.Forms?displayProperty=fullName>Reference k rozhraní API