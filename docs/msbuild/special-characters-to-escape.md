---
title: Speciální řídicí znaky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d263344b84ad93cc582d05112c08d2bad1aa998
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632443"
---
# <a name="special-characters-to-escape"></a>Speciální řídicí znaky
Speciální znaky musí být uvozena pouze v případě, že mají zvláštní význam v kontextu, ve kterém se používají. Například hvězdičku (*) je speciální znak pouze v atributech definici položky "Zahrnout" a "Vyloučit", nebo ve volání <xref:Microsoft.Build.Tasks.CreateItem>. Ve všech ostatních případech hvězdička je považován za literál hvězdičku. Zatímco nepotřebujete řídicí hvězdičky z obou stran kdekoli v souborech projektu, učiníte tak neškodí.

 Použití notace %\<xx > místo speciální znaky, kde \<xx > představuje šestnáctkovou hodnotu znaku standardu ASCII. Například pokud chcete použít hvězdičku (*) jako literální znak, použijte hodnotu `%2A`.

 Úplný seznam speciální řídicí znaky takto:

|Znak|Popis|
|---------------|-----------------|
|%|Znak procent, slouží jako odkaz na metadata.|
|$|Znak dolaru, používá k odkazování na vlastnosti.|
|@|Znak, slouží jako odkaz na seznamy položek.|
|(|Levou (otevírací), použít v seznamech.|
|)|Zavřít závorky používané seznamy.|
|`| Apostrof (nebo značky zaškrtnutí), použít v podmínkách a jiných výrazech.|
|;|Středník, oddělovač seznamu.|
|?|Otazník, zástupný znak při popisu specifikace souboru v části zahrnout/vyloučit položky.|
|*|Hvězdička, zástupný znak při popisu specifikace souboru v části zahrnout/vyloučit položky.|

## <a name="see-also"></a>Viz také:
- [Postupy: Speciální řídicí znaky v nástroji MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)