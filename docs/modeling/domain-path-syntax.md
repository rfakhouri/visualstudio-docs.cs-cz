---
title: "Syntaxe cesty domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, domain path
ms.assetid: 945994f9-72b9-42e0-81b2-e5fb3d0e282d
caps.latest.revision: "25"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d32cef09adef982f22aa46a72ab71cd1e7ec8568
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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
 [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md)