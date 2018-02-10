---
title: "MSBuild speciálních znaků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e1d7dc27d4a831e8e0a54cada37fcfdb94afd718
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] si vyhrazuje některé znaky pro speciální použití v konkrétní kontexty. Stačí vyhnuli takové znaky, pokud chcete použít jako literál v kontextu, ve kterém jsou rezervované. Například hvězdičku má zvláštní význam jenom v `Include` a `Exclude` atributů definice položky a v jeho voláních `CreateItem`. Pokud chcete hvězdičku vypadaly jako hvězdičkou v jednom z těchto kontexty, musí ho vyhnuli. V každé kontextu zadejte hvězdičku, kam má být zobrazen.  
  
 Abyste se vyhnuli zvláštní znak, použijte syntaxi %*xx*, kde *xx* představuje šestnáctkové hodnoty ASCII znaku. Další informace najdete v tématu [postup: vyhnuli speciální znaky v nástroji MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).  
  
## <a name="special-characters"></a>Speciální znaky  
 Následující tabulka uvádí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] speciální znaky:  
  
|**Znak**|**ASCII**|**Vyhrazené využití**|  
|-------------------|---------------|------------------------|  
|%|%25|Odkazování na metadata|  
|$|%24|Odkazování na vlastnosti|  
|@|%40|Odkazující položky seznamů|  
|'|%27|Podmínky a jiné výrazy|  
|;|%3B|Oddělovač seznamu|  
|?|% 3F|Zástupný znak pro názvy souborů v `Include` a `Exclude` atributy|  
|*|% 2A|Zástupný znak pro použití v názvech souborů v `Include` a `Exclude` atributy|  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)   
 [Položky](../msbuild/msbuild-items.md)