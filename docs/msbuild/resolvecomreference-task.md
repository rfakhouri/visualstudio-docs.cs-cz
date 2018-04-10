---
title: Resolvecomreference – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveComReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveCOMReference task
- ResolveCOMReference task [MSBuild]
ms.assetid: c9bf5fcf-6453-40ea-b50f-a212adc3e9b5
caps.latest.revision: 26
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 07381c84ec7213fe17aabb1db91cc1ab3be6188d
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="resolvecomreference-task"></a>ResolveComReference – úloha
Přebírá seznam jeden nebo více názvy knihovny typů, nebo soubory .tlb a řeší tyto knihoven typů do umístění na disku.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `ResolveCOMReference` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DelaySign`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, umístí veřejný klíč v sestavení. Pokud `false`, plně podepisuje sestavení.|  
|`EnvironmentVariables`|Volitelné `String[]` parametr.<br /><br /> Pole dvojic proměnných prostředí, oddělených symboly rovná se. Tyto proměnné jsou předávány vytvářený tlbimp.exe a aximp.exe kromě nebo selektivně přepsání, blokovat regulární prostředí...|  
|`ExecuteAsTool`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, spouští tlbimp.exe a aximp.exe z příslušná cílová framework out-of-proc ke generování sestavení nezbytné obálku. Tento parametr umožňuje cílení na více.|  
|`IncludeVersionInInteropName`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, verze typelib budou zahrnuty do obálky název. Výchozí hodnota je `false`.|  
|`KeyContainer`|Volitelné `String` parametr.<br /><br /> Určuje kontejner, který obsahuje veřejného a privátního<br /><br /> pár klíčů.|  
|`KeyFile`|Volitelné `String` parametr.<br /><br /> Určuje položku, která obsahuje veřejného a privátního<br /><br /> pár klíčů.|  
|`NoClassMembers`|Volitelné `Boolean`parametr.|  
|`ResolvedAssemblyReferences`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje odkazy na sestavení vyřešený.|  
|`ResolvedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje plně kvalifikovaný soubory na disku, které odpovídají fyzické umístění knihovny typů, které byly poskytnuty jako vstup pro tuto úlohu.|  
|`ResolvedModules`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]`parametr.|  
|`SdkToolsPath`|Volitelné <xref:System.String?displayProperty=fullName> parametr.<br /><br /> Pokud `ExecuteAsTool` je `true`, tento parametr musí být nastaven na cestu k sadě SDK nástroje cílové verzi framework.|  
|`StateFile`|Volitelné `String` parametr.<br /><br /> Určuje soubor mezipaměti pro komponenty modelu COM časová razítka. Pokud není přítomný, každé spuštění se znova vygeneruje všechny obálky.|  
|`TargetFrameworkVersion`|Volitelné `String` parametr.<br /><br /> Určuje verzi rozhraní projektu target framework.<br /><br /> Výchozí hodnota je `String.Empty`. což znamená, že žádné filtrování založené na rozhraní target framework odkaz.|  
|`TargetProcessorArchitecture`|Volitelné `String` parametr.<br /><br /> Určuje upřednostňovaný cíl architekturu procesoru. Byl předán příznak /machine tlbimp.exe po překladu.<br /><br /> Hodnota parametru musí být členem skupiny <xref:Microsoft.Build.Utilities.ProcessorArchitecture>.|  
|`TypeLibFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje cestu souboru knihovny typu COM odkazů na. Položky, které jsou zahrnuté v tomto parametru může obsahovat metadata položky. Další informace najdete v části "TypeLibFiles Metadata položky" níže.|  
|`TypeLibNames`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje názvy knihoven typ k vyřešení. Položky, které jsou součástí tento parametr musí obsahovat metadata některé položky. Další informace najdete v části "TypeLibNames Metadata položky" níže.|  
|`WrapperOutputDirectory`|Volitelné `String` parametr.<br /><br /> Umístění na disku, kde je umístěn generovaného sestavení vzájemné spolupráce. Pokud tato metadata položky není zadán, používá se úloha absolutní cestu k adresáři, kde je umístěn soubor projektu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="typelibnames-item-metadata"></a>Metadata položky TypeLibNames  
 Následující tabulka popisuje dostupné položky metadat pro předaný položky `TypeLibNames` parametr.  
  
|Metadata|Popis|  
|--------------|-----------------|  
|`GUID`|Požadovaná položka metadat.<br /><br /> Identifikátor GUID pro knihovny typů. Pokud není zadán tato metadata položky, že se úloha nezdaří.|  
|`VersionMajor`|Požadovaná položka metadat.<br /><br /> Hlavní verze knihovny typů. Pokud není zadán tato metadata položky, že se úloha nezdaří.|  
|`VersionMinor`|Požadovaná položka metadat.<br /><br /> Vedlejší verze knihovny typů. Pokud není zadán tato metadata položky, že se úloha nezdaří.|  
|`LocaleIdentifier`|Nepovinná položka metadat.<br /><br /> Identifikátor národního prostředí (nebo LCID) pro knihovny typů. To je zadán jako 32bitovou hodnotu, která identifikuje lidského jazyk preferované uživatele, oblasti nebo aplikace. Pokud tato metadata položky není zadán, použije úloha výchozí identifikátor národního prostředí "0".|  
|`WrapperTool`|Nepovinná položka metadat.<br /><br /> Určuje obálku nástroj, který se používá ke generování sestavení obálku pro tento typ knihovny. Pokud tato metadata položky není zadán, použije úloha výchozí nástroj obálku z "tlbimp". Jsou k dispozici, malá a velká písmena výběr knihovny TypeLib:<br /><br /> -   `Primary`: Tento nástroj obálku použijte, pokud chcete použít pro komponenty modelu COM již generovaného primární spolupracující sestavení. Použijete-li tento nástroj obálky, nezadávejte výstupního adresáře obálky, vzhledem k tomu, které způsobí, že úloha selhání.<br />-   `TLBImp`: Tento nástroj obálku můžete používejte ke generování sestavení vzájemné spolupráce pro komponenty modelu COM.<br />-   `AXImp`: Tento nástroj obálku můžete používejte ke generování sestavení vzájemné spolupráce pro ovládací prvek ActiveX.|  
  
## <a name="typelibfiles-item-metadata"></a>Metadata položky TypeLibFiles  
 Následující tabulka popisuje dostupné položky metadat pro předaný položky `TypeLibFiles` parametr.  
  
|Metadata|Popis|  
|--------------|-----------------|  
|`WrapperTool`|Nepovinná položka metadat.<br /><br /> Určuje obálku nástroj, který se používá ke generování sestavení obálku pro tento typ knihovny. Pokud tato metadata položky není zadán, použije úloha výchozí nástroj obálku z "tlbimp". Jsou k dispozici, malá a velká písmena výběr knihovny TypeLib:<br /><br /> -   `Primary`: Tento nástroj obálku použijte, pokud chcete použít pro komponenty modelu COM již generovaného primární spolupracující sestavení. Použijete-li tento nástroj obálky, nezadávejte výstupního adresáře obálky, vzhledem k tomu, které způsobí, že úloha selhání.<br />-   `TLBImp`: Tento nástroj obálku můžete používejte ke generování sestavení vzájemné spolupráce pro komponenty modelu COM.<br />-   `AXImp`: Tento nástroj obálku můžete používejte ke generování sestavení vzájemné spolupráce pro ovládací prvek ActiveX.|  
  
> [!NOTE]
>  Další informace, které zadáte k jednoznačné identifikaci knihovny typů, tím větší možnosti, že úloha bude odkazující na správný soubor na disku.  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)