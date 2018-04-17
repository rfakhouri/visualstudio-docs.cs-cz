---
title: Syntaxe cesty domény | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain path
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 3bac81f79b2639a7b1b4f93055855981d4c30786
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="domain-path-syntax"></a>Syntaxe cesty domény
K vyhledání konkrétní prvky v modelu DSL definice použít syntaxe jazyka XPath.  
  
 Normálně nemáte pracovat přímo s tuto syntaxi. Pokud se objeví v DSL podrobnosti nebo vlastnosti – okno, můžete klikněte na šipku dolů a pomocí editoru cestu. Cesta se však zobrazí v tomto formuláři v poli po použití editoru.  
  
 Cesta domény má následující podobu:  
  
 *RelationshipName.PropertyName/! Role*  
  
 ![CommentReferencesSubjects – odkazová referenční vztah](../modeling/media/dsl_reference.png "dsl_reference")  
  
 Syntaxe prochází stromu modelu. Například relace domény **CommentReferencesSubjects – odkazová** na obrázku výše **témata** role. Segment cesty **/! Subjectt** Určuje, že cesta k dokončení u elementů přistupovat prostřednictvím **témata** role.  
  
 Každý segment začíná název domény relace. Pokud traversal z elementu relaci, segmentu cesty se zobrazí jako *Relationship.PropertyName*. Pokud ke směrování pomocí odkazu na element, segmentu cesty se zobrazí jako *vztah /! RoleName*.  
  
 Lomítka samostatné syntaxe cesty. Každý segment cesty je směrování z se element odkazu (instance relace) nebo odkaz na element. Segmenty cesty v párech opakovaně zobrazit. Jeden segment cesty představuje směrování z elementu na odkaz, a další segment představuje směrování z odkazu na element na druhém konci. (Odkaz může být také zdroje nebo cíle relace sám sebe).  
  
 Název, který používáte pro element propojení směrování je hodnota role `Property Name`. Název, který používáte pro prvek odkazu směrování je cílová role.  
  
## <a name="see-also"></a>Viz také  
 [Porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md)