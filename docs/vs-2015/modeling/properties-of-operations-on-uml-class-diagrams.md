---
title: Vlastnosti operací v UML diagramech tříd | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.logicalclassdiagram.operation.properties
helpviewer_keywords:
- UML, element properties
ms.assetid: 4128f3e2-3a51-4edf-b3e4-b7f170a32f6b
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9d53c44a70818739e02c34071fd81b8bdfdec87f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54790516"
---
# <a name="properties-of-operations-on-uml-class-diagrams"></a>Vlastnosti operací v diagramech tříd UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V diagramu tříd UML lze přidat *operace* u tříd a rozhraní. Operace je metoda nebo funkce, která může provádět instance třídy nebo rozhraní.  

 Chcete-li přidat operaci, klikněte pravým tlačítkem na třídu nebo rozhraní, přejděte na **přidat**a potom klikněte na tlačítko **operace**.  

 Pokud operace třídy v diagramu nejsou viditelné, klikněte na Rozbalit dvojitou šipku v horní části třídy nebo rozhraní. Pokud se zobrazí **operace** záhlaví, klikněte na tlačítko **[+]** tím rozbalíte operace.  

## <a name="signature-of-an-operation"></a>Podpis operace  
 Podpis operace je řádek text, který představuje třídu nebo rozhraní v diagramu tříd UML. Má následující tvar:  

 \+ OperationName (Parametr1: Type1 [*]...) : Vlastnost ReturnType [\*]  

 \+ označuje public viditelnost. Povolené hodnoty jsou – (privátní), # (chráněný), ~ (balíček).  

 `OperationName` je podtržený, pokud **Is Static** vlastnost má hodnotu true a je kurzíva-li **je abstraktní** vlastnost má hodnotu true.  

 `: ReturnType` je vynechána, pokud je definována bez návratového typu.  

 `[*]` označuje násobnosti atributu parametr nebo návratový typ elementu. To je vynechána, pokud je násobnost 1.  

 V části Další úplný popis těchto vlastností.  

## <a name="properties"></a>Vlastnosti  
 Toto jsou vlastnosti operace ve třídě nebo rozhraní v diagramu tříd UML.  

 Pokud chcete zobrazit vlastnosti operace, klikněte pravým tlačítkem na operaci v dané třídy nebo rozhraní v diagramu a klikněte na **vlastnosti**. Vlastnosti se zobrazí v **vlastnosti** okna.  


|      Vlastnost       |   Výchozí    |                                                                                                                                                                                 Popis                                                                                                                                                                                 |
|---------------------|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **Název**       | (nové jméno) |                                                                                                                                                                Musí být jedinečné v rámci nadřazeného typu.                                                                                                                                                                 |
|   **Parametry**    |    (žádné)    |      Seznam, který má tvar <em>název</em>**:**<em>typ</em>**,** <em>název</em>**:**  <em>Typ</em>**,...** Klikněte na tlačítko **[...]**  můžete upravit seznam.<br /><br /> Typy mohou být primitivní typy nebo typy, které jsou definovány v modelu. Pokud zadáte název pro nový typ této vlastnosti, typ se přidají do **nespecifikované typy** části Průzkumníku modelů UML.      |
|   **Návratový typ**   |    (žádné)    |                                                                               **(žádné)** , nebo primitivní typ nebo typ, který je definován v modelu. Pokud zadáte název pro nový typ této vlastnosti, typ se přidají do **nespecifikované typy** části Průzkumníku modelů UML.                                                                                |
| **Vstupních**  |    (žádné)    |                                                                                                                         Určení vztahu mezi stav systému před a po spuštění operace nepovinnou podmínku.                                                                                                                         |
|  **Předběžné podmínky**  |    (žádné)    |                                                                                                                            Nepovinnou podmínku určující předpoklady o stavu systému před provedením operace zahájí vykonávání.                                                                                                                            |
| **Text podmínek** |    (žádné)    |                                                                                                                                                       Volitelná omezení pro hodnoty vrácené operací.                                                                                                                                                       |
|   **Viditelnost**    |    Public    |                  Povolené hodnoty a znaky, které se zobrazí v signatuře jsou:<br /><br /> **+ Veřejné** – viditelné globálně<br /><br /> **-Privátní** – nejsou viditelné mimo vlastnící typ<br /><br /> **# Chráněné** – viditelné pro typy odvozené od vlastníka<br /><br /> **~ Balíček** – viditelné pro ostatní typy v rámci stejného balíčku.                   |
|    **podpis**    |  +*Name*()   |                                                                                      Shrnuje viditelnost, název, parametry a návratový typ této operace. Tyto vlastnosti můžete změnit úpravou signatura v diagramu nebo úpravou jednotlivé vlastnosti.                                                                                      |
|   **Pracovní položky**    | související 0 |                                                                                                  Počet přidružené pracovní položky. Jen pro čtení.<br /><br /> Další informace najdete v tématu [propojení prvků modelu a pracovních položek](../modeling/link-model-elements-and-work-items.md).                                                                                                  |
|   **Souběžnost**   |  Sekvenční  | **Sekvenční** – tato operace je nebo bude navrženy bez řízení souběžnosti. Souběžné volání této operace může způsobit selhání.<br /><br /> **Chráněné** -operace bude automaticky blokovat, dokud další výskyty byly dokončeny.<br /><br /> **Souběžné** – operace je navržený tak, aby více volání k němu mohou být prováděna současně. |
|    **Je statická**    |    False     |                                                                                                  Při hodnotě true se tato operace se sdílí mezi všechny instance tohoto typu.<br /><br /> Při hodnotě true se název operace podtržené kde se zobrazí v diagramu.                                                                                                   |
|   **Je abstraktní**   |    False     |                                                                                                                                        Pokud je hodnota true, není žádný kód související s touto operací. Proto vlastnící třída je abstraktní.                                                                                                                                         |
|     **List**     |    False     |                                                                                                                                              Návrhář si klade za cíl, že tuto operaci nelze přepsat v odvozených třídách.                                                                                                                                              |
|    **Je dotaz**     |    False     |                                                                                                 Při hodnotě true se nebudou provedeny žádné významné změny stavu systému touto operací. Proto ji je možné, například v rámci testu ke kontrole stavu systému.                                                                                                  |
|  **Násobnost**   |      1       |                                 **1** – samostatná hodnota ze zadaného typu.<br /><br /> **0..1** -může být `null`.<br /><br /> \* -kolekci hodnot zadaného typu.<br /><br /> **1..\\**  \* - kolekce obsahuje alespoň jednu hodnotu.<br /><br /> *n* `..` *m* – kolekce, která obsahuje mezi `n` a `m` hodnoty.                                  |
|   **Je seřazen**    |    False     |                                                                                                                                             Při hodnotě true se vytváří kolekce sekvenční seznamu. Pro **násobnost** více než 1.                                                                                                                                              |
|    **Je jedinečný**    |    False     |                                                                                                                                         Pokud je hodnota true, nejsou v kolekci žádné duplicitní hodnoty. Pro **násobnost** více než 1.                                                                                                                                         |

## <a name="see-also"></a>Viz také  
 [Diagramy tříd UML: Referenční dokumentace](../modeling/uml-class-diagrams-reference.md)   
 [Vlastnosti typů v diagramech tříd UML](../modeling/properties-of-types-on-uml-class-diagrams.md)   
 [Vlastnosti atributů v diagramech tříd UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md)   
 [Vlastnosti přidružení v diagramech tříd UML](../modeling/properties-of-associations-on-uml-class-diagrams.md)   
 [Diagramy tříd UML: Pokyny](../modeling/uml-class-diagrams-guidelines.md)
