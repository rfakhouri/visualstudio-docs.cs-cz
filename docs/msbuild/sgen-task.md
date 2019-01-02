---
title: SGen – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#SGen
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SGen task [MSBuild]
- MSBuild, SGen task
ms.assetid: 22c5ade4-4159-4667-b891-0c1aa06f4df5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 54f3f19617e71137f6f318f62d13c9119727f5f0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53939651"
---
# <a name="sgen-task"></a>SGen – úloha
Vytvoří sestavení serializace XML pro typy v zadaném sestavení. Tato úloha obtéká nástroj Generátor serializátor XML (*Sgen.exe*). Další informace najdete v tématu [nástroj Generátor serializátor XML (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).  

## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SGen` úloh.  


| Parametr | Popis |
|-----------------------------| - |
| `BuildAssemblyName` | Vyžaduje `String` parametru.<br /><br /> Sestavení pro generování kódu serializace pro. |
| `BuildAssemblyPath` | Vyžaduje `String` parametru.<br /><br /> Cesta k sestavení pro generování kódu serializace pro. |
| `DelaySign` | Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, určuje, že chcete li plně podepsané sestavení. Pokud `false`, určuje, že chcete pouze umístit veřejný klíč v sestavení.<br /><br /> Tento parametr nemá žádný vliv, pokud nejsou použity s buď `KeyFile` nebo `KeyContainer` parametru. |
| `KeyContainer` | Volitelné `String` parametru.<br /><br /> Určuje kontejner obsahující pár klíčů. Toto podepíše sestavení tak, že vloží veřejný klíč do manifestu sestavení. Úloha se pak podepíše konečné sestavení soukromým klíčem. |
| `KeyFile` | Volitelné `String` parametru.<br /><br /> Určuje dvojici klíčů nebo veřejný klíč k podepsání sestavení. Kompilátor vloží veřejný klíč do manifestu sestavení a poté podepíše konečné sestavení soukromým klíčem. |
| `Platform` | Volitelné `String` parametru.<br /><br /> Získá nebo nastaví platformě kompilátoru sloužící ke generování výstupního sestavení. Tento parametr může mít hodnotu `x86`, `x64`, nebo `anycpu`. Výchozí hodnota je `anycpu`. |
| `References` | Volitelné `String[]` parametru.<br /><br /> Určuje sestavení, která je odkazováno dle typy vyžadujících serializace XML. |
| `SdkToolsPath` | Volitelné `String` parametru.<br /><br /> Určuje cestu k sadě SDK nástroje, jako *resgen.exe*. |
| `SerializationAssembly` | Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje sestavení vygenerované serializace. |
| `SerializationAssemblyName` | Volitelné `String` parametru.<br /><br /> Určuje název generovaného serializace sestavení. |
| `ShouldGenerateSerializer` | Vyžaduje `Boolean` parametru.<br /><br /> Pokud `true`, SGen – úloha by měl generovat sestavení serializace. |
| `Timeout` | Volitelné `Int32` parametru.<br /><br /> Určuje množství času, v milisekundách, po jejichž uplynutí je spustitelný soubor s úkolem ukončen. Výchozí hodnota je `Int.MaxValue`, která udává, že neexistuje žádný časový limit. |
| `ToolPath` | Volitelné `String` parametru.<br /><br /> Určuje umístění, kde bude úloha načtení základní spustitelného souboru (*sgen.exe*). Pokud není tento parametr zadán, použije úloha instalační cestu sady SDK odpovídající verzi rozhraní framework, na kterém běží [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. |
| `Types` | Volitelné `String[]` parametru.<br /><br /> Získá nebo nastaví seznam pro generování kódu serializace pro konkrétní typy. SGen – vygeneruje kód serializace pouze u typů. |
| `UseProxyTypes` | Vyžaduje `Boolean` parametru.<br /><br /> Pokud `true`, SGen – úloha generuje kód serializace pouze pro typy XML webové služby serveru proxy. |

## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)