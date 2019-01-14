---
title: Průzkumník schémat XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 2fc39e98-b194-456b-a452-cfafb0a52d66
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 37733ddb09fb726c5407888af91db2bc32713799
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/14/2019
ms.locfileid: "54268497"
---
# <a name="xml-schema-explorer"></a>Průzkumník schémat XML

**Průzkumníka schémat XML** je integrovaná s Microsoft Visual Studio a Editor souborů XML umožňují pracovat s schémat schématu XML definice jazyk (XSD). Při otevření souboru schématu XML **schéma nastaveno** se zobrazí v uzlu **Průzkumníka schémat XML**. Všechny zahrnuté, importované nebo Předefinovaná schémata pro cílový soubor, stejně jako všechny soubory, které jsou odkazovány prostřednictvím `include` nebo `import` příkazu, se také zobrazují v **Průzkumníka schémat XML**.

 **Průzkumníka schémat XML** umožňuje provést následující:

-   Získejte rychlý přehled o sadě schémat.

-   Procházení a přejděte strom.

-   Proveďte – klíčové slovo a specifické pro schéma vyhledávání. Další informace najdete v tématu [hledání v sadě schémat](../xml-tools/searching-the-schema-set.md).

-   Přidat výsledky hledání pro zobrazení grafu nebo zobrazení modelu obsahu

-   Seřaďte podle pořadí dokumentů, typ nebo název stromu. Další informace najdete v tématu [řazení, filtrování a seskupování](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md).

-   Otevření editoru XML a přejděte do umístění kódu v souboru XSD. Další informace najdete v tématu [integrace s editorem XML](../xml-tools/integration-with-xml-editor.md).

-   Generovat ukázkový soubor XML pro globální prvky.

**Průzkumníka schémat XML** zobrazuje hierarchická schématu nastavit pomocí stromového zobrazení. **Průzkumníka schémat XML** také poskytuje vyhledávání, filtrování, navigace a řazení. Pro přístup **Průzkumníka schémat XML**, proveďte jednu z následujících akcí:

-   Pokud používáte [zobrazení Start](../xml-tools/start-view.md), klikněte na tlačítko **Průzkumníka schémat XML** odkaz.

-   Pokud používáte [zobrazení grafu](../xml-tools/graph-view.md) nebo [zobrazení modelu obsahu](../xml-tools/content-model-view.md) a mít uzly ve vašem pracovním prostoru, použijte nabídku kontextu (klikněte pravým tlačítkem) a vyberte **Průzkumníka schémat XML**.

-   Můžete také vybrat **Průzkumníka schémat XML** z **zobrazení** nabídky.

-   Můžete přistupovat **Průzkumníka schémat XML** z *.vb* soubor, který má přidružené k literálu XML v jazyce Visual Basic *XSD* souboru. Chcete-li zobrazit schéma nastavte v **Průzkumníka schémat XML**, klikněte pravým tlačítkem na uzel XML literál XML nebo import oboru názvů XML a vyberte **zobrazit v Průzkumníkovi schémat** příkaz. Další informace najdete v tématu [literály integrace XML s Průzkumníkem schémat XML](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md).

## <a name="tree-view"></a>Stromové zobrazení
 **Průzkumníka schémat XML** zobrazí předem kompilaci schématu nastavení informací o ve stromové struktuře. Stromové struktury je uspořádaný následujícím způsobem:

-   Na nejvyšší úrovni je schéma, nastavte uzel.

-   Na druhé úrovni obsahuje obory názvů.

-   Na třetí úrovni obsahuje soubory.

-   Čtvrtý úrovni obsahuje globální uzly. To může zahrnovat prvky, skupiny, komplexní typy, jednoduché typy, atributy, skupiny atributů a `include`, `import`, a `redefine` příkazy.

Následuje příklad stromové struktury:

![Průzkumník schémat XML](../xml-tools/media/xmlschemaexplorer.gif)

## <a name="selection-and-activation"></a>Výběr a aktivace
 Pokud chcete zvýraznit a vyberte uzel, klikněte na jednou Průzkumník schémat.

 Pokud chcete aktivovat uzel, poklepejte na něj nebo stiskněte klávesu **Enter** při výběru uzlu.

-   Aktivace uzel otevře soubor, ve kterém je definována tento uzel (Pokud soubor ještě není otevřený) a vybere uzel v souboru.

-   Aktivace uzel souboru (Pokud není již otevřený), otevře se vybraný soubor a zvýrazní `<schema>` uzlu.

-   Aktivace SchemaSet nebo uzel oboru názvů nemá žádný účinek.

## <a name="drag-and-drop-nodes"></a>Přetáhnout myší uzly
 Můžete přetáhnout a globální uzly, uzly souborových a uzly oboru názvů do zobrazení o návrháři XSD. Pokud je aktuální zobrazení nastaveno [zobrazení Start](../xml-tools/start-view.md), tažení uzlu k zobrazení se otevře [zobrazení grafu](../xml-tools/graph-view.md). Pokud je aktuální zobrazení nastaveno [zobrazení modelu obsahu](../xml-tools/content-model-view.md) nebo zobrazení grafu, zobrazení se nezmění, pokud je vyřadit uzel problém napravit.

 Odstranit soubory v zobrazení přidá všechny globální uzly v souboru, který má [pracovní prostor návrháře XSD](../xml-tools/xml-schema-designer-workspace.md). Vyřazení obory názvů pro zobrazení přidá všechny globální uzly v oboru názvů do pracovního prostoru. Pracovní prostor se sdílí mezi všech zobrazení.

 Je nelze přetáhnout myší místní uzly nebo importy.

## <a name="see-also"></a>Viz také:

- [Postupy: Přidání uzlů do pracovního prostoru z Průzkumníka schémat XML](../xml-tools/how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer.md)