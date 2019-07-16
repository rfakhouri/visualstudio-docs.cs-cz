---
title: Metadata známé položky nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, item metadata
- MSBuild, well-known item metadata
ms.assetid: b5e791b5-c68f-4978-ad8a-9247d03bb6c0
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1bb2e53102221194dc829df162c44bbf04378b28
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68154085"
---
# <a name="msbuild-well-known-item-metadata"></a>Metadata známé položky nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Následující tabulka popisuje metadata přiřazená každé položce při vytvoření. V každém příkladu byl použit následující deklarace položky zahrnout soubor `C:\MyProject\Source\Program.cs` v projektu.  
  
```  
<ItemGroup>  
    <MyItem Include="Source\Program.cs" />  
</ItemGroup>  
```  
  
|Metadata položky|Popis|  
|-------------------|-----------------|  
|%(FullPath)|Obsahuje úplnou cestu položky. Příklad:<br /><br /> `C:\MyProject\Source\Program.cs`|  
|%(RootDir)|Obsahuje kořenový adresář položky. Příklad:<br /><br /> `C:\`|  
|%(FileName)|Obsahuje název souboru položky bez přípony. Příklad:<br /><br /> `Program`|  
|%(Extension)|Obsahuje příponu názvu souboru položky. Příklad:<br /><br /> `.cs`|  
|%(RelativeDir)|Obsahuje cesty zadané v `Include` atribut až po konečné zpětné lomítko (\\). Příklad:<br /><br /> `Source\`|  
|%(Directory)|Obsahuje adresář položky bez kořenového adresáře. Příklad:<br /><br /> `MyProject\Source\`|  
|%(RecursiveDir)|Pokud `Include` atribut obsahuje zástupný znak \* \*, určují tato metadata část cesty, která nahrazuje zástupný znak. Další informace o zástupných znacích naleznete v tématu [jak: Výběr souborů pro sestavení](../msbuild/how-to-select-the-files-to-build.md).<br /><br /> Pokud složka *C:\MySolution\MyProject\Source\\*  obsahuje soubor Program.cs a pokud se tato položka obsahuje soubor projektu:<br /><br /> `<ItemGroup>`<br /><br /> `<MyItem Include="C:\**\Program.cs" />`<br /><br /> `</ItemGroup>`<br /><br /> poté hodnotu `%(MyItem.RecursiveDir)` by *MySolution\MyProject\Source\\* .|  
|%(Identity)|Položka zadaná v `Include` atribut... Příklad:<br /><br /> `Source\Program.cs`|  
|%(ModifiedTime)|Obsahuje časové razítko od poslední návštěvy, položka byla změněna. Příklad:<br /><br /> `2004-07-01 00:21:31.5073316`|  
|%(CreatedTime)|Obsahuje časové razítko od vytvoření položky. Příklad:<br /><br /> `2004-06-25 09:26:45.8237425`|  
|%(AccessedTime)|Obsahuje časové razítko od posledního přístupu k položce.<br /><br /> `2004-08-14 16:52:36.3168743`|  
  
## <a name="see-also"></a>Viz také  
 [Položky](../msbuild/msbuild-items.md)   
 [Dávkové zpracování](../msbuild/msbuild-batching.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
