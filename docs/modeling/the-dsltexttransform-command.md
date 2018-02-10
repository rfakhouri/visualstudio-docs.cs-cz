---
title: "Příkaz DslTextTransform | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 24a3f292633b915678bad232a4a671c7906e15cb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="the-dsltexttransform-command"></a>Příkaz DslTextTransform
DslTextTransform.cmd je skript, který volá TextTransform.exe a spustí pomocí běžné možnosti. DslTextTransformation.cmd můžete použít k automatizaci noční sestavení vaší [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projekty. Další informace najdete v tématu [generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd se nachází v následujícím adresáři:  
  
 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**  
  
 Jako vstup pro DslTextTransform.cmd můžete určit následující argumenty:  
  
-   Výstupní adresář projektu modelu domény.  
  
-   Výstupní adresář projektu definice návrháře.  
  
-   Umístění textového souboru šablony.  
  
 DslTextTransform.cmd zpracuje zadaný textový soubor šablony pomocí procesory direktiv výchozí a sestavení. Pokud vytvoříte vlastní procesory direktiv, můžete vytvořit vlastní dávkový soubor, který volá TextTransform.exe. V tento dávkový soubor můžete zadat vaše sestavení a přidružené vlastní procesory direktiv.