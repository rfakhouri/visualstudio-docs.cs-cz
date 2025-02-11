---
title: Reference k rozhraní API pro rozšíření modelování UML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 12eadb9844df5da78b11367708fed715f1c13672
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68159675"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>Referenční dokumentace k rozhraní API pro rozšíření modelování UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete napsat kód programu číst a upravovat modely, které vytvoříte pomocí sady Visual Studio. Reference k rozhraní API poskytuje informace o konkrétní třídách, které vám pomůžou. Další informace o orientovaných na úlohy, naleznete v tématech v části [modelů a diagramů UML rozšířit](../modeling/extend-uml-models-and-diagrams.md). Pokud chcete zobrazit, které verze sady Visual Studio podporují modelech UML, naleznete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="assemblies"></a>Sestavení  
  
|Assembly|To umožňuje provést|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.Uml.Interfaces.dll|– Čtení a změnit prvky modelu, jako je například IUseCase IAssociation a tak dále.<br />-Procházet vztahy mezi elementy.<br /><br /> Obory názvů a typy odpovídají těm, které jsou definovány ve specifikaci UML.|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|– Vytváření nových instancí elementů modelu<br />– Přístup a upravit tvary a diagramy.|  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření modelů a diagramů UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Referenční dokumentace rozhraní API k sadě Modeling SDK pro Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
