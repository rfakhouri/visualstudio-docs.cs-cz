---
title: 'Sekvenční diagramy UML: Referenční dokumentace | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.sequencediagram.diagram
- vs.teamarch.UMLModelExplorer.sequencediagram
- vs.teamarch.sequencediagram.toolbox
helpviewer_keywords:
- diagrams - modeling, sequence
- sequence diagrams
- UML diagrams, sequence
- diagrams - modeling, UML sequence
- UML, sequence diagrams
ms.assetid: 366fc324-aeeb-4894-bd13-ec2e40754b8e
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3990d43ae11db3db8eb792883ba62a030cde3a2f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62548558"
---
# <a name="uml-sequence-diagrams-reference"></a>Sekvenční diagramy UML: Odkaz
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V sadě Visual Studio *sekvenční diagram* ukazuje interakce, která představuje pořadí zpráv mezi instance tříd, komponenty, subsystémy nebo objekty actor. Čas toky dolů diagramu a zobrazuje tok řízení z jeden účastník do jiného. Pomocí sekvenčních diagramů můžete vizualizovat instancí a událostech namísto třídy a metody. Více než jednu instanci stejného typu může zobrazit v diagramu. Více než jeden výskytu stejná zpráva se může zobrazit i.  
  
 Sekvenční diagramy UML jsou součástí modelu UML a existují jenom v rámci projektů pomocí modelování UML. K vytvoření sekvenčního diagramu UML na **architektura** nabídky, klikněte na tlačítko **nové UML nebo diagramu vrstev**. Další informace o tom, jak vytvořit a nakreslete [sekvenčních diagramech UML](../modeling/uml-sequence-diagrams-guidelines.md) nebo [diagramů pomocí modelování UML](../modeling/edit-uml-models-and-diagrams.md) obecně.  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="reading-sequence-diagrams"></a>Čtení sekvenčních diagramů  
 Následující tabulka popisuje prvky, které se zobrazí v diagramu. Přečtěte si další informace o těchto [elementy vlastnosti](../modeling/properties-of-elements-on-uml-sequence-diagrams.md).  
  
 ![Části sekvenčního diagramu](../modeling/media/uml-sequence.png "UML_Sequence")  
  
|**Obrazec**|**Element**|**Popis**|  
|---------------|-----------------|---------------------|  
|1|**Životnost**|Svislá čára, která představuje posloupnost událostí, ke kterým dochází v účastníka během interakce, při postupuje čas řádek dolů. Tímto účastníkem může být instance třídy, komponenty nebo aktéra.|  
|2|**objekt actor**|Člena, který je externím systému, které vyvíjíte.<br /><br /> Můžete vytvořit objekt actor symbol, který se zobrazí v horní části stránky životnosti nastavením jeho **objektu Actor** vlastnost.|  
|3|**Synchronní zprávy**|Odesílatel čeká na odpověď na zprávu synchronní před pokračováním. Diagram znázorňuje volání a vrácení. Synchronní zprávy se používá k reprezentování běžné funkce volání v rámci programu, jakož i jiné druhy zprávy, které se chovají stejným způsobem.|  
|4|**Asynchronních zpráv**|Zpráva, která nevyžaduje odpovědi, než bude pokračovat odesílatele. Asynchronní zprávy ukazuje pouze volání od odesílatele. Použijte k reprezentaci komunikace mezi oddělených vláknech či vytváření nového vlákna.|  
|5|**Provádění události**|Svislé stín obdélníku, který se zobrazí na účastníka životnost a představuje dobu, když je účastník provádění operace.<br /><br /> Provádění začne, kde účastníka přijme zprávu. Pokud se synchronní zpráva zahajující zprávu, provedení končí na «vrátit» šipku zpět do odesílatele.|  
|6|**Zprávy zpětné volání**|Zpráva, která vrátí zpět na účastníka, který čeká na vrácení v dřívějším volání. Výsledný výskyt spuštění se zobrazí nad stávající.|  
|7|**Vlastní zpráva**|Zprávy od účastníka na sebe sama. Výsledný výskyt spuštění se zobrazí nad odesílání spuštění.|  
|8|**Vytvoření zprávy**|Zpráva, která vytvoří účastníka. Když účastník obdrží zprávu vytvořit, měla by být první, které obdrží.|  
|9|**Nalezená zpráva**|Asynchronní zprávy z neznámé nebo neurčené účastníka.|  
|10|**Ztracenou zprávu**|Asynchronní zprávy k neznámé nebo neurčené účastníka.|  
|11|**Komentář**|Komentář může být připojen do libovolného bodu na životnost.|  
|12|**Použitím interakce**|Vloží sekvenci zpráv, které jsou definovány do jiného diagramu.<br /><br /> Vytvoření **použitím interakce**, klikněte na nástroje a poté proveďte operaci přetažení přes životnosti, které chcete zahrnout.|  
|13|**Kombinovaného fragmentu**|Kolekce fragmenty. Každý fragment možné uzavřít do uvozovek jednu nebo více zpráv. Existují různé druhy kombinované fragmenty. Další informace najdete v tématu [Describe toku řízení pomocí fragmentů v sekvenčních diagramech UML](../modeling/describe-control-flow-with-fragments-on-uml-sequence-diagrams.md).<br /><br /> Chcete-li vytvořit fragment, klikněte pravým tlačítkem na zprávu, přejděte na **obklopit fragmentem**a potom klikněte na typ fragment.|  
|14|**Fragment Guard**|Je možné stanovit příslušné Určuje, zda dojde k fragment podmínku.<br /><br /> Pro nastavení ochranného zařízení, vyberte fragment, pak vyberte ochranného zařízení a zadejte hodnotu.|  
|**X**|**Událost zničení**|Reprezentuje bod, ve kterém je objekt odstraněný nebo nedostupný. Zobrazí se na konci každé životnosti.|  
||**Interakce**|Kolekce zpráv a životnosti, který se zobrazí v sekvenčním diagramu. Chcete-li zobrazit vlastnosti interakci, musíte vybrat v **Průzkumníku modelů UML**.|  
||**Sekvenční Diagram**|Diagram zobrazující interakci. Chcete-li zobrazit její vlastnosti, klikněte na prázdnou část diagramu. **Poznámka:**  Názvy sekvenčního diagramu interakce, že se zobrazí, a soubor, který obsahuje diagram může být jiný.|  
  
## <a name="see-also"></a>Viz také  
 [Sekvenční diagramy UML: Pokyny](../modeling/uml-sequence-diagrams-guidelines.md)   
 [Úpravy modelů a diagramů UML](../modeling/edit-uml-models-and-diagrams.md)   
 [Diagramy případů použití UML: Referenční dokumentace](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagramy tříd UML: Referenční dokumentace](../modeling/uml-class-diagrams-reference.md)   
 [Diagramy komponent UML: Referenční dokumentace](../modeling/uml-component-diagrams-reference.md)   
 [Diagramy komponent UML: Referenční dokumentace](../modeling/uml-component-diagrams-reference.md)
