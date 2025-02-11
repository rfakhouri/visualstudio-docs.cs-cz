---
title: Error – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
manager: jillfra
ms.openlocfilehash: b220d12b872a81cba5f46bd14fdebafaa58cf4a1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201815"
---
# <a name="error-task"></a>Error – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)
