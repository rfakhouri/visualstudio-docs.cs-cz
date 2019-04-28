---
title: Vlastnosti elementů v diagramech komponent UML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.componentdiagram.shapes.properties
helpviewer_keywords:
- component diagrams, properties
- UML, element properties
ms.assetid: fa0a9460-6675-4642-aa00-50f8719a892d
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c7f3f30d08fb62defec5e783da286e968a6b17c9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444428"
---
# <a name="properties-of-elements-on-uml-component-diagrams"></a>Vlastnosti elementů v diagramech komponent UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Každý prvek v diagramu v diagramu komponent UML má vlastnosti. Pokud chcete zobrazit vlastnosti elementu, klikněte pravým tlačítkem na elementu v diagramu nebo v **Průzkumníku modelů UML** a potom klikněte na tlačítko **vlastnosti**. Vlastnosti se zobrazí v **vlastnosti** okna.  
  
> [!NOTE]
> Toto téma se věnuje vlastnosti elementů v diagramech komponent UML. Další informace o tom, jak přečíst diagramy komponent UML, naleznete v tématu [diagramy komponent UML: Referenční dokumentace](../modeling/uml-component-diagrams-reference.md). Další informace o tom, jak nakreslit diagramy komponent UML, naleznete v tématu [diagramy komponent UML: Pokyny pro](../modeling/uml-component-diagrams-guidelines.md).  
  
## <a name="properties-of-elements"></a>Vlastnosti elementů  
  
|Vlastnost|Výchozí|Prvek|Popis|  
|--------------|-------------|-------------|-----------------|  
|**Název**|Výchozí název|Všechny|Určuje element.|  
|**Kvalifikovaný název**|Namespace:: Název|Všechny|Jednoznačně identifikuje elementu.<br /><br /> Komponenta nebo název typu předchází s kvalifikovaným názvem balíčku, který jej obsahuje.<br /><br /> Část nebo názvu portu předchází s kvalifikovaným názvem komponenty, které jej vlastní.|  
|**Pracovní položky**|související 0|Všechny|Počet pracovních položek, které jsou spojené s tímto prvkem. Přidružení pracovních položek, naleznete v tématu [propojení prvků modelu a pracovních položek](../modeling/link-model-elements-and-work-items.md).|  
|**Popis**|(žádné)|Všechny|Můžete nastavit obecné poznámky o prvku tady.|  
|**Barva**|(výchozí nastavení pro typ)|Komponenty, součást, delegování, část sestavení|Barva obrazce. Na rozdíl od dalších vlastností Toto je barva obrazce spíše než prvku modelu, který tvar zobrazí.|  
|**Instance je vytvořena nepřímo**|Pravda|Součást|Komponenta existuje pouze jako artefakt návrhu. V době běhu existují jen jeho části.|  
|**Je abstraktní**|False|Součást|Definice komponenty lze použít pouze jako generalizace, ze kterého může být specializovaná další komponenty.|  
|**Viditelnost**|Public|Komponenty, část, Port|**Veřejné** – viditelné globálně.<br /><br /> **Balíček** – viditelné v rámci balíčku.<br /><br /> **Privátní** – viditelné v rámci vlastní komponenty.<br /><br /> **Chráněné** – viditelný na komponenty odvozené od vlastníka.|  
|**Typ**|Zadejte při vytvoření|Část<br /><br /> Port|Typ součásti je komponenta nebo třídy.<br /><br /> Typ portu je rozhraní.|  
|**Násobnost**|1|Část<br /><br /> Port|Označuje, kolik instancí zadaného typu tvoří součást nadřazené komponenty.<br /><br /> `1` -právě jeden.<br /><br /> `0..1` -one nebo žádný.<br /><br /> `*` -kolekci libovolného počtu.<br /><br /> `n..m` -kolekce z n m instancí.|  
|**Je chování**|False|Port|Při hodnotě true se zprávy k tomuto portu jsou zpracovávány aktivity nebo operací, které jsou popsány v rámci komponenty, ne jejích částí.|  
|**Je služba**|False|Port|Při hodnotě true se tento port je součástí rozhraní publikované této součásti.|  
|**LinkedPackage**|Model|diagram|Výchozí obor názvů pro elementy přidané do tohoto diagramu.|  
  
## <a name="see-also"></a>Viz také  
 [Diagramy případů použití UML: Referenční dokumentace](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagramy případů použití UML: Pokyny](../modeling/uml-use-case-diagrams-guidelines.md)
