---
title: 'Postupy: Řídicí znaky v nástroji MSBuild | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d6b10c8f4b2658acc3dd4dfa113c8edd8f1de5b2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59665712"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Postupy: Zápis speciálních znaků pomocí escape sekvence v MSBuildu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Některé znaky mají speciální význam v [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] soubory projektu. Příklady znaků: středníkem (;) a hvězdičky (*). Úplný seznam těchto speciálních znaků, naleznete v tématu [speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md).  
  
 Chcete-li použít tyto speciální znaky jako literály v souboru projektu, se musí zadat pomocí syntaxe %*xx*, kde *xx* představuje znak šestnáctkové hodnoty ASCII.  
  
## <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild  
 Jedna je například použití speciálních znaků v `Include` atribut položky seznamů. Například následující seznam položek deklaruje dvě položky: `MyFile.cs` a `MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs;MyClass.cs"/>  
```  
  
 Pokud chcete deklarovat, který obsahuje středníkem v názvu položky, je nutné použít %*xx* syntaxe řídicí středník a zabránit [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] z deklarace dvou samostatných položek. Například následující položka řídicí sekvence středník a deklaruje jednu položku s názvem `MyFile.cs;MyClass.cs`.  
  
```  
<Compile Include="MyFile.cs%3BMyClass.cs"/>  
```  
  
#### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>Chcete-li použít speciální znak MSBuild jako literální znak  
  
-   Použití notace %*xx* místo speciální znaky, kde *xx* představuje šestnáctkovou hodnotu znaku standardu ASCII. Například pokud chcete použít hvězdičku (*) jako literální znak, použijte hodnotu `%2A`.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Nástroj MSBuild](msbuild.md) [položky](../msbuild/msbuild-items.md)
