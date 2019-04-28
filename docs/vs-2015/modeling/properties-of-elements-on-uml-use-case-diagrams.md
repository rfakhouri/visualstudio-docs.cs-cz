---
title: Vlastnosti elementů v UML použijte diagramy případu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.usecasediagram.artifact.properties
- vs.teamarch.usecasediagram.shapes.properties
helpviewer_keywords:
- use case diagrams, properties
ms.assetid: 2728fb26-a275-4fce-8a2c-5a78af6bee04
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b52afab80bc22c03dc5ff980b937cad53869f5db
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444416"
---
# <a name="properties-of-elements-on-uml-use-case-diagrams"></a>Vlastnosti elementů v diagramech případů použití UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Každý prvek v diagramu v diagramu případu použití UML má vlastnosti. Pokud chcete zobrazit vlastnosti elementu, klikněte pravým tlačítkem na elementu v diagramu nebo v **Průzkumníku modelů UML** a potom klikněte na tlačítko **vlastnosti**. Vlastnosti se zobrazí v **vlastnosti** okna.  
  
> [!NOTE]
> Toto téma se věnuje vlastnosti elementů v diagramech případů použití UML. Další informace o tom, jak přečíst diagramy činnosti UML, naleznete v tématu [diagramy případů použití UML: Referenční dokumentace](../modeling/uml-use-case-diagrams-reference.md). Další informace o tom, jak nakreslit diagramy činnosti UML, naleznete v tématu [diagramy případů použití UML: Pokyny pro](../modeling/uml-use-case-diagrams-guidelines.md).  
  
## <a name="properties-of-elements"></a>Vlastnosti elementů  
  
|Vlastnost|Výchozí|Prvek|Popis|  
|--------------|-------------|-------------|-----------------|  
|**Název**|Výchozí název|Všechny|Určuje element.|  
|**Kvalifikovaný název**|Balíček:: Název|Všechny|Jednoznačně identifikuje elementu. Předponu úplný název balíčku, který jej obsahuje.|  
|**Pracovní položky**|související 0|Všechny|Počet pracovních položek, které jsou spojené s tímto prvkem. Přidružení pracovních položek, naleznete v tématu [propojení prvků modelu a pracovních položek](../modeling/link-model-elements-and-work-items.md).|  
|**Popis**|(žádné)|Všechny|Můžete nastavit obecné poznámky o prvku tady.|  
|**Barva**|(výchozí)|Všechny|Barva obrazce. Na rozdíl od dalších vlastností, to není vlastnost elementu, který tvar zobrazí.|  
|**Cesta k bitové kopii**|(žádné)|objekt actor|Cesta k souboru obrázku, který se má použít místo výchozí ikona objektu actor. Ikona by měl být soubor prostředků v rámci projektu sady Visual Studio.|  
|**Témata**|(žádné)|Případ použití|Podsystém nebo jiný typ, který vlastní případu použití.<br /><br /> Můžete ho nastavit tak, že v podsystému v diagramu případu použití.|  
|**Viditelnost**|Public|Používat subsystém případu, objekt Actor|**Veřejné** – viditelné globálně.<br /><br /> **Balíček** – viditelné v rámci balíčku.|  
|**IsAbstract**|False|Používat subsystém případu, objekt Actor|Při hodnotě true se typ nedá vytvořit instance a slouží jako základ pro specializaci pomocí jiné definice.|  
|**Instance je vytvořena nepřímo**|Pravda|Subsystém|Subsystém existuje pouze jako artefakt návrhu. V době běhu existují jen jeho části.|  
|**Hypertextový odkaz**|(žádné)|Artefakt|Adresa URL nebo cesta diagramu nebo dokument, ke kterému artefaktu s odkazem.|  
  
 Seznam vlastností asociace, naleznete v tématu [vlastnosti přidružení v UML diagramech tříd](../modeling/properties-of-associations-on-uml-class-diagrams.md).  
  
## <a name="see-also"></a>Viz také  
 [Diagramy případů použití UML: Referenční dokumentace](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagramy případů použití UML: Pokyny](../modeling/uml-use-case-diagrams-guidelines.md)
