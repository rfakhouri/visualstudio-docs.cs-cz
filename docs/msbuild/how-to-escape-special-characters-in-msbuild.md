---
title: 'Postupy: vyhnuli speciální znaky v nástroji MSBuild | Microsoft Docs'
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43981b2ba736318aaf53ee6ed47bb39ef930557f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Postupy: Zápis speciálních znaků pomocí escape sekvence v nástroji MSBuild
Některé znaky mají zvláštní význam [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu. Mezi příklady znaky patří středníkem (;) a hvězdičky (*). Úplný seznam tyto speciální znaky, najdete v části [speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md).  
  
 Chcete-li použít tyto speciální znaky jako literály v souboru projektu, se musí být určena pomocí syntaxe %*xx*, kde *xx* představuje šestnáctkové hodnoty ASCII znaku.  
  
## <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild  
 Jedna je například použití speciálních znaků v `Include` atribut položky seznamů. Například v následujícím seznamu položky deklaruje dvě položky: `MyFile.cs` a `MyClass.cs`.  
  
```xml  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Pokud chcete deklarovat položku, která obsahuje středníkem v názvu, musíte použít %*xx* syntaxe vyhnuli středník a zabránit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] z deklarace dvě samostatné položky. Například následující položku řídicí sekvence středník a deklaruje jednu položku s názvem `MyFile.cs;MyClass.cs`.  
  
```xml  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>Použít speciální znak MSBuild jako literál znak  
  
-   Použít zápis %*xx* místo speciální znak, kde *xx* představuje šestnáctkové hodnoty znaků ASCII. Například jako literál znak používat hvězdičku (*), použijte hodnotu `%2A`.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild](../msbuild/msbuild.md) [položky](../msbuild/msbuild-items.md)