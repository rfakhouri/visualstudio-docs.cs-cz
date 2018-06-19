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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e325ab2d5a5a54a9aaf8378753ccbe8f3a72a5a8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31569186"
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