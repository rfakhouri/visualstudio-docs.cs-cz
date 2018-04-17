---
title: Getreferenceassemblypaths – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06cd1da1a30e4d19981465dbe65218fe337e1fef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="getreferenceassemblypaths-task"></a>GetReferenceAssemblyPaths – úloha
Vrátí odkaz na sestavení cesty různé architektury.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `GetReferenceAssemblyPaths` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|Volitelné `String[]` výstupní parametr.<br /><br /> Vrací cestu, na základě `TargetFrameworkMoniker` parametr. Pokud `TargetFrameworkMoniker` má hodnotu null nebo prázdné, bude tato cesta `String.Empty`.|  
|`FullFrameworkReferenceAssemblyPaths`|Volitelné `String[]` výstupní parametr.<br /><br /> Vrací cestu, na základě `TargetFrameworkMoniker` parametr, bez ohledu část profilu přezdívka. Pokud `TargetFrameworkMoniker` má hodnotu null nebo prázdné, bude tato cesta `String.Empty`.|  
|`TargetFrameworkMoniker`|Volitelné `String` parametr.<br /><br /> Určuje Přezdívka framework cíl, který je přidružen cesty sestavení odkazů.|  
|`RootPath`|Volitelné `String` parametr.<br /><br /> Určuje kořenovou cestu sloužící ke generování referenční cesty pro sestavení.|  
|`BypassFrameworkInstallChecks`|Volitelné <xref:System.Boolean> parametr.<br /><br /> Pokud `true`, obchází základní kontroly, `GetReferenceAssemblyPaths` provádí ve výchozím nastavení zajistit, že jsou nainstalovány určité modul runtime rozhraní, v závislosti na cílové rozhraní.|  
|`TargetFrameworkMonikerDisplayName`|Volitelné `String` výstupní parametr.<br /><br /> Určuje zobrazovaný název pro cílový framework přezdívka.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)