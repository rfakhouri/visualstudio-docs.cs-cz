---
title: T4 Direktivy textové šablony | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
ms.assetid: 6898ee02-ebb2-4635-a4e9-350774c13cf2
caps.latest.revision: 83
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e079b21c3a85f883351808b8defda6d0d68619f7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666858"
---
# <a name="t4-text-template-directives"></a>T4 – direktivy textových šablon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [direktivy textové šablony T4](https://docs.microsoft.com/visualstudio/modeling/t4-text-template-directives).  
  
Direktivy poskytují pokyny stroji, který provádí transformace textových šablon.  
  
 Direktivy mají následující syntaxi:  
  
```  
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>  
```  
  
 Všechny hodnoty atributů musejí být uzavřeny do dvojitých uvozovek. Pokud samotná hodnota obsahuje uvozovky, musejí být uvozeny znakem \.  
  
 Direktivy jsou zpravidla prvním prvkem v souboru šablony nebo vkládaném souboru. Neměli byste je umísťovat dovnitř bloku kódu `<#...#>`, ani za blok funkcí třídy `<#+...#>`.  
  
 [T4 – direktiva Template](../modeling/t4-template-directive.md)  
 ```  
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 [T4 – direktiva Parameter](../modeling/t4-parameter-directive.md)  
 ```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 [T4 – direktiva Output](../modeling/t4-output-directive.md)  
 ```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)  
 ```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 [T4 – direktiva Import](../modeling/t4-import-directive.md)  
 ```  
<#@ import namespace="namespace" #>  
```  
  
 [T4 – direktiva Include](../modeling/t4-include-directive.md)  
 ```  
<#@ include file="filePath" #>  
```  
  
 [T4 – direktiva CleanUpBehavior](../modeling/t4-cleanupbehavior-directive.md)  
 ```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Navíc můžete vytvářet své vlastní direktivy. Další informace najdete v tématu [vytváření vlastních procesorů textových šablon T4 – direktiva](../modeling/creating-custom-t4-text-template-directive-processors.md). Pokud pomocí sady Visualization and Modeling SDK vytvoříte jazyk domény (DSL), vygeneruje se procesor direktiv jako součást tohoto kódu DSL.



