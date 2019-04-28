---
title: Použít Návrháře tříd
ms.date: 05/08/2018
ms.topic: conceptual
f1_keywords:
- vs.classdesigner.diagram
helpviewer_keywords:
- Class Designer [Visual Studio]
- Class Designer, about Class Designer
- types [Visual Studio], viewing
- classes [Visual Studio], viewing
- class designer
ms.assetid: 40ed2c9d-0ce0-4b95-ad78-5dec2065ccea
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee4910471693a2941ec9548773a2f50e443a639b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975571"
---
# <a name="design-and-view-classes-and-types-with-class-designer"></a>Návrh a zobrazení tříd a typů pomocí návrháře tříd

Návrh, vizualizace a Refaktorovat třídy a další typy v kódu pomocí **návrhář tříd** v sadě Visual Studio. Použít diagramy tříd k vytvoření a úprava tříd ve vaší C#, Visual Basic nebo C++ projektu. Můžete také použít diagramy tříd pochopit strukturu projektu lepší nebo reorganizovat váš kód.

## <a name="what-you-can-do-with-class-diagrams"></a>Co můžete dělat s diagramy tříd

- **Návrh**: Úpravy kódu úpravou diagramu tříd. Přidat nové prvky a odstraňte nežádoucí. Vaše změny se projeví v kódu.

- **Vizualizujte**: Struktura projektu pochopit zobrazením třídy v projektu v diagramu. Přizpůsobte diagramu tak, aby se mohli soustředit na podrobnosti o projektu, které vám nejvíce záleží. Uložení diagramu pro pozdější použití pro demonstraci nebo dokumentaci.

- **Refaktorovat**: Přepište metody, přejmenujte identifikátory, refaktorace parametry a implementovat rozhraní a abstraktní třídy.

## <a name="view-types-and-relationships"></a>Zobrazení typů a vztahů

Diagramy tříd zobrazí podrobnosti o typech, například jejich základní členy a vztahy mezi nimi. Vizualizace z těchto entit je dynamický náhled do kódu. To znamená, že můžete upravit typy v návrháři a přejděte na téma úpravy projeví ve zdrojovém kódu entity. Podobně diagram tříd je udržovat synchronizované s změny provedené na soubory kódu.

> [!NOTE]
> Pokud váš projekt obsahuje diagram třídy a váš projekt odkazuje na typ, který se nachází v jiném projektu, diagram tříd dokud při sestavení projektu pro daný typ odkazovaný typ nezobrazuje. Podobně diagram nezobrazuje změny kódu externí entitu dokud je znovu sestavit projekt pro danou entitu.

## <a name="class-diagram-workflow"></a>Diagram třídy pracovního postupu

Diagramy tříd můžete vám pomůže pochopit struktura třídy projektů. Tyto projekty může být vytvořen jinými vývojáři nebo jenom potřebujete občerstvit na projektu, které jste sami vytvořili. Diagramy tříd můžete upravit, sdílet a prezentovat informace o projektu s ostatními.

Prvním krokem při zobrazení informací o projektu je vytvoření diagramu tříd, který se zobrazí, co chcete zobrazit. Další informace najdete v tématu [přidání diagramu tříd](how-to-add-class-diagrams-to-projects.md). Můžete vytvořit více diagramů tříd v projektu, který slouží k zobrazení různých zobrazení projektu, zvolená podmnožinu typů v projektu nebo podmnožinu vybrané členy typů.

Kromě definujete, co se zobrazí každý diagram tříd, můžete také změnit způsob, který se zobrazí informace; Další informace najdete v tématu [jak: Přizpůsobení diagramů tříd](how-to-customize-class-diagrams.md).

Po mají doladíte jeden nebo více diagramů tříd, zkopírují se do dokumentů Microsoft Office a vytisknout nebo exportovat jako soubory obrázků. Další informace najdete v tématu [jak: Kopírování elementů diagramu tříd do dokumentu Microsoft Office](how-to-copy-class-diagram-elements-to-a-microsoft-office-document.md), [jak: Tisk diagramů tříd](how-to-print-class-diagrams.md) a [jak: Export diagramů tříd jako obrázky](how-to-export-class-diagrams-as-images.md).

> [!NOTE]
> Návrhář tříd nesleduje umístění zdrojových souborů, takže změna strukturu projektu nebo přesunutí zdrojové soubory v projektu může způsobit návrhář tříd ke ztrátě informací o typu, zejména zdrojový typ definice typu základní třídy a přidružení typů. Může se objevit chyba, jako je **je návrhář tříd nemůže zobrazit tento typ**. Pokud tak učiníte, přetáhněte do diagramu tříd znovu a znovu zobrazit přemístění nebo upravila zdrojový kód.

## <a name="see-also"></a>Viz také:

- [Funkce editoru kódu](../writing-code-in-the-code-and-text-editor.md)
- [Mapování závislostí napříč vaším řešením](../../modeling/map-dependencies-across-your-solutions.md)