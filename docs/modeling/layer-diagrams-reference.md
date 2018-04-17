---
title: 'Diagramy závislost: Referenční | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1a4ca32a85db34fa03a2ec5e52446707938b0304
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="dependency-diagrams-reference"></a>Diagramy závislost: referenční dokumentace
V sadě Visual Studio, můžete použít *diagram závislostí* můžete vizualizovat podrobný, logické architekturu systému. Diagram závislostí organizuje fyzické artefakty ve vašem systému do logické, abstraktní skupin nazývaných *vrstvy*. Tyto vrstvy popisují hlavní úlohy, které provádějí artefakty nebo hlavní součásti systému. Jednotlivé úrovně může také obsahovat vnořené vrstvy, které popisují podrobnější úlohy.  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Můžete zadat určené nebo existující závislosti mezi vrstvami. Tyto závislosti, které jsou reprezentovány jako dvojice šipek, znamenat vrstvy, které můžete použít nebo používají funkci reprezentována jiných vrstev. Uspořádání systému do vrstvy, které popisují odlišné role a funkce, diagram závislostí může pomoci snadno pochopit, opakovaně používat a údržbu vašeho kódu.  
  
 Pomocí závislosti diagram můžete provádět následující úlohy:  
  
-   Komunikaci existující, nebo určený Logická architektura vašeho systému.  
  
-   Zjistit konflikty mezi váš stávající kód a určený architektura.  
  
-   Vizualizace dopad změny na určený architektuře při Refaktorovat, aktualizovat nebo momentální systému.  
  
-   Posílení určený architektura během vývoj a údržba kódu včetně ověřování pomocí vašeho změnami a sestavení operace.  
  
 Toto téma popisuje elementy, které můžete použít v diagramu závislostí. Podrobné informace o tom, jak vytvořit a kreslení diagramů závislostí, najdete v části [diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md). Další informace o rozvrstvení vzorech, najdete [postupy společnosti lokality](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
## <a name="reading-dependency-diagrams"></a>Čtení diagramy závislostí  
 ![Elementů v diagramech závislostí](../modeling/media/uml_layerrefreading.png "UML_LayerRefReading")  
  
 Následující tabulka popisuje prvky, které můžete použít v diagramu závislostí.  
  
|**Obrazce**|**Element**|**Popis**|  
|---------------|-----------------|---------------------|  
|1|**Vrstva**|Logické skupiny fyzické artefakty ve vašem systému. Tyto artefakty může být obory názvů, projekty, tříd, metod a tak dále.<br /><br /> Informace o artefakty, které jsou propojeny s vrstvou, otevřete místní nabídku pro vrstvy a zvolte **zobrazení odkazy** otevřete **Explorer vrstvy**.<br /><br /> Další informace najdete v tématu [Explorer vrstvy](#Explorer).<br /><br /> -   **Je zakázané Namespace závislosti** -Určuje, že artefakty přidružené k této vrstvy nemůže záviset na zadaných oborů názvů.<br />-   **Je zakázané obory názvů** -Určuje, že artefakty přidružené k této vrstvy nesmí patří do zadaných oborů názvů.<br />-   **Požadované obory názvů** -Určuje, že artefakty přidružené k této vrstvy musí patřit do jedné ze zadaných oborů názvů.|  
|2|**závislosti**|Označuje, že jedné vrstvy můžete použít funkci v jiné vrstvě, ale ne naopak.<br /><br /> -   **Směr** -Určuje směr, závislosti.|  
|3|**Obousměrné závislostí**|Označuje, že jedné vrstvy můžete použít funkci v jiné vrstvě a naopak.<br /><br /> -   **Směr** -Určuje směr, závislosti.|  
|4|**Komentář**|Slouží k přidání obecné poznámky diagram nebo elementy v diagramu.|  
|5|**Odkaz na komentáře**|Slouží k propojení komentáře k prvkům v diagramu.|  
  
##  <a name="Explorer"></a> Průzkumník vrstvy  
 Jednotlivé úrovně můžete propojit artefakty ve vašem řešení, jako jsou projekty, třídy, obory názvů, soubory projektu a dalšími částmi váš software. Číslo na vrstvě zobrazuje číslo artefaktů, které jsou propojeny s vrstvě. Ale při čtení počtu artefakty na vrstvě, mějte na paměti následující:  
  
-   Pokud vrstva odkazuje na artefakt, který obsahuje jiné artefakty, ale vrstva není propojena přímo s jiným artefaktem, pak číslo obsahuje pouze propojené artefakty. Jiné artefakty jsou však zahrnuty do analýzy během ověřování vrstvy.  
  
     Pokud je vrstva například spojena s jedním oborem názvů, pak počet propojených artefaktů je 1, přestože obor názvů obsahuje třídy. Pokud vrstva obsahuje rovněž propojení s jednotlivými třídami v oboru názvů, bude počet zahrnovat propojené třídy.  
  
-   Pokud například vrstva obsahuje jiné vrstvy, které jsou spojeny s artefakty, pak je vrstva kontejneru také propojena s těmito artefakty, i když číslo vrstvy kontejneru tyto artefakty neobsahuje.  
  
 Další informace o propojení vrstev a artefaktů najdete v tématu:  
  
-   [Diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md)  
  
-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
#### <a name="to-examine-the-linked-artifacts"></a>K prozkoumání propojené artefaktů.  
  
-   Diagram závislostí, otevřete místní nabídku pro jednu nebo více vrstev a zvolte **zobrazení odkazy**.  
  
     **Vrstvy Průzkumníka** otevře a zobrazuje artefaktů, které jsou propojeny s vybrané vrstvy. **Vrstvy Průzkumníka** má sloupec, který znázorňuje všechny vlastnosti odkazy artefaktů.  
  
    > [!NOTE]
    >  Pokud nevidíte všechny tyto vlastnosti, rozbalte **vrstvy Explorer** okno.  
  
    |**Sloupec v Průzkumníku vrstvy**|**Popis**|  
    |----------------------------------|---------------------|  
    |**Kategorie**|Druh artefaktů, jako je například třída, obor názvů, zdrojový soubor a tak dále|  
    |**Vrstva**|Vrstva, která odkazuje na artefaktu|  
    |**Podporuje ověřování**|Pokud **True**, pak proces ověření vrstvy, můžete ověřit, že projekt odpovídá závislosti do nebo z tohoto elementu.<br /><br /> Pokud **False**, potom na odkaz není součástí procesu ověření vrstvy.<br /><br /> Další informace najdete v tématu [diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md).|  
    |**Identifikátor**|Odkaz na propojenou artefaktů|  
  
## <a name="see-also"></a>Viz také  
 [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)
