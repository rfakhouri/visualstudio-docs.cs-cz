---
title: "Metadata známé položky nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, item metadata
- MSBuild, well-known item metadata
ms.assetid: b5e791b5-c68f-4978-ad8a-9247d03bb6c0
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0a31e21ad45f03a3f72b49131f660988da71efee
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-well-known-item-metadata"></a>Metadata známé položky nástroje MSBuild
Následující tabulka popisuje metadata přiřazené každá položka po vytvoření. V obou příkladech byl použit následující položky deklaraci zahrnout soubor `C:\MyProject\Source\Program.cs` v projektu.  
  
```xml  
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
|%(RelativeDir)|Cesta zadaná v obsahuje `Include` atribut až do konečného zpětné lomítko (\\). Příklad:<br /><br /> `Source\`|  
|%(Directory)|Obsahuje adresář položky bez kořenový adresář. Příklad:<br /><br /> `MyProject\Source\`|  
|%(RecursiveDir)|Pokud `Include` atribut obsahuje zástupného \* \*, určuje tato metadata část cesty, která nahradí zástupný znak. Další informace o zástupné znaky, najdete v části [postup: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md).<br /><br /> Pokud složka *C:\MySolution\MyProject\Source\\*  obsahuje soubor Program.cs, a pokud projekt soubor obsahuje tuto položku:<br /><br /> `<ItemGroup>`<br /><br /> `<MyItem Include="C:\**\Program.cs" />`<br /><br /> `</ItemGroup>`<br /><br /> pak hodnota `%(MyItem.RecursiveDir)` by *MySolution\MyProject\Source\\*.|  
|%(Identity)|Položky určené v `Include` atribut... Příklad:<br /><br /> `Source\Program.cs`|  
|%(ModifiedTime)|Obsahuje časové razítko z posledního položka byla změněna. Příklad:<br /><br /> `2004-07-01 00:21:31.5073316`|  
|%(CreatedTime)|Obsahuje časové razítko z vytvoření položky. Příklad:<br /><br /> `2004-06-25 09:26:45.8237425`|  
|%(AccessedTime)|Obsahuje časové razítko z čas posledního přístupu k položce.<br /><br /> `2004-08-14 16:52:36.3168743`|  
  
## <a name="see-also"></a>Viz také  
 [Položky](../msbuild/msbuild-items.md)   
 [Dávkování](../msbuild/msbuild-batching.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)