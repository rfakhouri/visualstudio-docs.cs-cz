---
title: "SGen – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#SGen
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SGen task [MSBuild]
- MSBuild, SGen task
ms.assetid: 22c5ade4-4159-4667-b891-0c1aa06f4df5
caps.latest.revision: "11"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4ebb6579cd4ac4ee96547bbc7d70f471f17e4e53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sgen-task"></a>SGen – úloha
Vytvoří sestavení serializace XML pro typy v zadaném sestavení. Tato úloha zabalí nástroje Generátor serializátor XML (Sgen.exe). Další informace najdete v tématu [nástroje Generátor serializátor XML (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SGen` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`BuildAssemblyName`|Požadované `String` parametr.<br /><br /> Sestavení pro generování kódu serializace pro.|  
|`BuildAssemblyPath`|Požadované `String` parametr.<br /><br /> Cesta k sestavení pro generování kódu serializace pro.|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje, že má plně podepsané sestavení. Pokud `false`, určuje, že chcete pouze umístit veřejný klíč v sestavení.<br /><br /> Tento parametr nemá žádný vliv, pokud není použita s buď `KeyFile` nebo `KeyContainer` parametr.|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje kontejner obsahující pár klíčů. To podepíše sestavení vložením veřejný klíč do manifestu. Úloha se pak se přihlaste konečné sestavení s privátním klíčem.|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje pár klíčů nebo veřejný klíč sloužící k podepsání sestavení. Kompilátor vloží veřejný klíč do manifestu sestavení a poté podepíše konečné sestavení soukromým klíčem.|  
|`Platform`|Volitelné `String` parametr.<br /><br /> Získá nebo nastaví platformou kompilátoru sloužící ke generování sestavení výstupu. Tento parametr může mít hodnotu `x86`, `x64`, nebo `anycpu`. Výchozí hodnota je `anycpu`.|  
|`References`|Volitelné `String[]` parametr.<br /><br /> Určuje sestavení, která je odkazováno dle typy vyžadujících serializace XML.|  
|`SdkToolsPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu k SDK nástroje, jako je například resgen.exe.|  
|`SerializationAssembly`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje sestavení serializace vygenerovaný.|  
|`SerializationAssemblyName`|Volitelné `String` parametr.<br /><br /> Určuje název sestavení vygenerovaný serializace.|  
|`ShouldGenerateSerializer`|Požadované `Boolean` parametr.<br /><br /> Pokud `true`, SGen – úloha měl generovat sestavení serializace.|  
|`Timeout`|Volitelné `Int32` parametr.<br /><br /> Určuje množství času, v milisekundách, po kterých je spustitelný soubor úlohy ukončen. Výchozí hodnota je `Int.MaxValue`, což označuje, že bez doby vypršení časového limitu.|  
|`ToolPath`|Volitelné `String` parametr.<br /><br /> Určuje umístění, ze kterých úloha načte základní spustitelný soubor (sgen.exe). Pokud není tento parametr zadán, použije úloha cesta instalace sady SDK odpovídající verzi rozhraní, které běží [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`Types`|Volitelné `String[]` parametr.<br /><br /> Získá nebo nastaví seznam pro generování kódu serializace pro konkrétní typy. SGen – vygeneruje kód serializace jenom pro tyto typy.|  
|`UseProxyTypes`|Požadované `Boolean` parametr.<br /><br /> Pokud `true`, SGen – úloha generuje kód serializace jenom pro typy XML webové služby serveru proxy.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)