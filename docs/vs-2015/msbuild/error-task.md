---
title: Error – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a7579a448a113c51a58e492da6ea9e7e4ca9ede
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666748"
---
# <a name="error-task"></a>Error – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Error – úloha](https://docs.microsoft.com/visualstudio/msbuild/error-task).  
  
  
Sestavení se zastaví a protokoly chybu na základě Vyhodnocená podmíněného příkazu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Error` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Code`|Volitelné `String` parametru.<br /><br /> Kód chyby, které chcete přidružit k chybě.|  
|`File`|Volitelné `String` parametru.<br /><br /> Název souboru, který obsahuje chybu. Pokud je k dispozici žádný název souboru, soubor obsahující chyby úkolů se použije.|  
|`HelpKeyword`|Volitelné `String` parametru.<br /><br /> Klíčové slovo nápovědy pro přidružení k chybě.|  
|`Text`|Volitelné `String` parametru.<br /><br /> Text chyby, která [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] protokoly, pokud `Condition` vyhodnotí jako parametr `true`.|  
  
## <a name="remarks"></a>Poznámky  
 `Error` Úloha umožňuje [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekty vydávat text chyby protokolovacích nástrojů a zastavit provádění sestavení.  
  
 Pokud `Condition` vyhodnotí jako parametr `true`, sestavení je zastavená a je zaznamenána chyba. Pokud `Condition` neexistuje parametr, se protokoluje chyby a sestavení zastaví provádění. Další informace o protokolování naleznete v tématu [získávání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ověřuje, že všechny požadované vlastnosti nastavené. Pokud nejsou nastavená, projektu vyvolá událost chyby a protokoly hodnotu `Text` parametr `Error` úloh.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Error  
            Text=" The 0 property must be set on the command line."  
            Condition="'$(0)' == ''" />  
        <Error  
            Text="The FREEBUILD property must be set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)



