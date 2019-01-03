---
title: Getreferenceassemblypaths – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 485b8f9c19a8a91d686b603ee1be9da70b6c78e1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987872"
---
# <a name="getreferenceassemblypaths-task"></a>Getreferenceassemblypaths – úloha
Vrátí odkaz na sestavení cesty různých platforem.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `GetReferenceAssemblyPaths` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|Volitelné `String[]` výstupní parametr.<br /><br /> Vrátí cestu, na základě `TargetFrameworkMoniker` parametru. Pokud `TargetFrameworkMoniker` má hodnotu null nebo být prázdný, tato cesta bude `String.Empty`.|  
|`FullFrameworkReferenceAssemblyPaths`|Volitelné `String[]` výstupní parametr.<br /><br /> Vrátí cestu, na základě `TargetFrameworkMoniker` parametr bez zohlednění část zástupný název profilu. Pokud `TargetFrameworkMoniker` má hodnotu null nebo být prázdný, tato cesta bude `String.Empty`.|  
|`TargetFrameworkMoniker`|Volitelné `String` parametru.<br /><br /> Určuje moniker cílového rozhraní, která souvisí s cesty referenčního sestavení.|  
|`RootPath`|Volitelné `String` parametru.<br /><br /> Určuje kořenová cesta pro generování cesta pro odkaz na sestavení.|  
|`BypassFrameworkInstallChecks`|Volitelné <xref:System.Boolean> parametru.<br /><br /> Pokud `true`, obchází základní kontroly, který `GetReferenceAssemblyPaths` provádí ve výchozím nastavení k zajištění, že určitá rozhraní modulu runtime jsou nainstalovány, v závislosti na cílové rozhraní.|  
|`TargetFrameworkMonikerDisplayName`|Volitelné `String` výstupní parametr.<br /><br /> Určuje zobrazovaný název pro moniker cílového rozhraní.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)