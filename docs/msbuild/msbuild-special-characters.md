---
title: MSBuild speciálních znaků | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c1a2f67204fd6df7c8eb12ce5f13e8d1f4ec29d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
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
|;|% 3B|Oddělovač seznamu|  
|?|% 3F|Zástupný znak pro názvy souborů v `Include` a `Exclude` atributy|  
|*|% 2A|Zástupný znak pro použití v názvech souborů v `Include` a `Exclude` atributy|  
  
## <a name="see-also"></a>Viz také  
 [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)   
 [Položky](../msbuild/msbuild-items.md)