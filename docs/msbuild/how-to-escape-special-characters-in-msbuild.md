---
title: 'Postupy: řídicí speciální znaky v nástroji MSBuild | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d921236fe44c7402bb26800c02624e2c391301a
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077063"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Postupy: řídicí speciální znaky v nástroji MSBuild
Některé znaky mají speciální význam v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu. Příklady znaků: středníkem (;) a hvězdičky (*). Úplný seznam těchto speciálních znaků, naleznete v tématu [speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md).  
  
 Chcete-li použít tyto speciální znaky jako literály v souboru projektu, se musí zadat pomocí syntaxe %\<xx >, kde \<xx > představuje znak šestnáctkové hodnoty ASCII.  
  
## <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild  
 Jedna je například použití speciálních znaků v `Include` atribut položky seznamů. Například následující seznam položek deklaruje dvě položky: *MyFile.cs* a *MyClass.cs*.  
  
```xml  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Pokud chcete deklarovat, který obsahuje středníkem v názvu položky, je nutné použít %\<xx > syntaxe řídicí středník a zabránit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] z deklarace dvou samostatných položek. Například následující položka řídicí sekvence středník a deklaruje jednu položku s názvem *MyFile.cs; MyClass.cs*.  
  
```xml  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>Chcete-li použít speciální znak MSBuild jako literální znak  
  
-   Použití notace %\<xx > místo speciální znaky, kde \<xx > představuje šestnáctkovou hodnotu znaku standardu ASCII. Například pokud chcete použít hvězdičku (*) jako literální znak, použijte hodnotu `%2A`.  
  
## <a name="see-also"></a>Viz také:  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Nástroj MSBuild](../msbuild/msbuild.md)   
 [Položky](../msbuild/msbuild-items.md)   
