---
title: "MSBuild speciálních znaků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
caps.latest.revision: "8"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 04b679ed649bc4fe01a2bccb08a8c5e137b6141d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]si vyhrazuje některé znaky pro speciální použití v konkrétní kontexty. Stačí vyhnuli takové znaky, pokud chcete použít jako literál v kontextu, ve kterém jsou rezervované. Například hvězdičku má zvláštní význam jenom v `Include` a `Exclude` atributů definice položky a v jeho voláních `CreateItem`. Pokud chcete hvězdičku vypadaly jako hvězdičkou v jednom z těchto kontexty, musí ho vyhnuli. V každé kontextu zadejte hvězdičku, kam má být zobrazen.  
  
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