---
title: Návrhář schématu XML integrace pomocí editoru XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 43d7a8e6-bd94-4407-a800-15a145c74223
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b2e2b7a9e6511faaa1941d65f6b328a07b10f79
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="integration-with-xml-editor"></a>Integrace s editoru XML

Návrhář schématu XML je integrovaná s editoru XML. Pokud upravíte soubor XSD v editoru XML, změna se projeví v [Explorer schématu XML](../xml-tools/xml-schema-explorer.md). Pokud máte [zobrazení grafu](../xml-tools/graph-view.md) nebo [zobrazení obsahu modelu](../xml-tools/content-model-view.md) otevřená, změna se také zobrazí existuje. Je možné přecházet mezi Návrhář schématu XML a Editor souborů XML následujícími způsoby:

-   V editoru XML, klikněte pravým tlačítkem na uzel a vyberte **zobrazit v Průzkumníku schématu XML**.

-   V zobrazení grafu a Explorer schématu XML, klikněte dvakrát na uzlu, nebo klikněte pravým tlačítkem na uzel a vyberte **kód zobrazení**. V zobrazení obsahu Model, klikněte pravým tlačítkem na uzel a vyberte **kód zobrazení**.

Následující snímek obrazovky ukazuje, že schéma XML otevřít v Průzkumníkovi schématu XML. Explorer schématu XML zobrazí schéma nastavit ve stromovém zobrazení. Editor souborů XML zobrazí textového zobrazení uzlu, který je aktuálně aktivní v Průzkumníku schématu XML.

![XSDDesignerWithXMLEditor](../xml-tools/media/xsddesignerwithxmleditor.gif)

Někdy je užitečné kódu v editoru XML a grafický Návrhář vedle sebe. Chcete-li zobrazit oba soubory ve stejnou dobu, klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **Návrhář zobrazení**. V nabídce Visual Studio Windows vyberte **nové vodorovné (nebo Vertical) skupina záložek**.

![XSDDesignerWithXMLEditorAndCMV](../xml-tools/media/xsddesignerwithxmleditorandcmv.gif)

## <a name="see-also"></a>Viz také

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)