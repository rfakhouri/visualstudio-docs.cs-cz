---
title: Nástroj MSBuild speciálních znaků | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- escape characters
- escape
- MSBuild Escape Characters
ms.assetid: 545e6a59-1093-4514-935e-78679a46fb3c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a87013ff3a1911caa667f7ba431e408fc87a98f4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004638"
---
# <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] rezervuje některé znaky pro speciální použití v určitém kontextu. Stačí dostala mimo tyto znaky, pokud chcete použít doslova v kontextu, ve kterém jsou vyhrazené. Například hvězdičku má zvláštní význam pouze v `Include` a `Exclude` atributy definici položky a ve voláních `CreateItem`. Pokud chcete hvězdičku jako hvězdičky v jednom z těchto kontextech, musíte je přeskočit. V každé další kontext zadejte hvězdičku, kde chcete, aby se zobrazí.

 K návratu speciální znak, použijte syntaxi %\<xx >, kde \<xx > představuje znak šestnáctkové hodnoty ASCII. Další informace najdete v tématu [jak: Řídicí znaky v nástroji MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).

## <a name="special-characters"></a>Speciální znaky
 Následující tabulka uvádí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] speciální znaky:

|**Znak**|**ASCII**|**Vyhrazené využití**|
|-------------------|---------------|------------------------|
|%|%25|Odkazování na metadata|
|$|%24|Odkazování na vlastnosti|
|@|%40|Referenční seznamy položek|
|\'|%27|Podmínky a jiných výrazech|
|;|%3B|Oddělovač seznamu|
|?|%3F|Zástupný znak pro názvy souborů v `Include` a `Exclude` atributy|
|*|% 2|Zástupný znak pro použití v názvech souborů v `Include` a `Exclude` atributy|

## <a name="see-also"></a>Viz také:
- [Rozšířené koncepty](../msbuild/msbuild-advanced-concepts.md)
- [Položky](../msbuild/msbuild-items.md)