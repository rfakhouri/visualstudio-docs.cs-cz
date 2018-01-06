---
title: "Příkaz DslTextTransform | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: "30"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 4b8c7040cabf05b30920654996891bc8d19f42db
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="the-dsltexttransform-command"></a>Příkaz DslTextTransform
DslTextTransform.cmd je skript, který volá TextTransform.exe a spustí pomocí běžné možnosti. DslTextTransformation.cmd můžete použít k automatizaci noční sestavení vaší [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projekty. Další informace najdete v tématu [generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd se nachází v následujícím adresáři:  
  
 **\<Cesta instalace sady Visual Studio SDK > \VisualStudioIntegration\Tools\Bin**  
  
 Jako vstup pro DslTextTransform.cmd můžete určit následující argumenty:  
  
-   Výstupní adresář projektu modelu domény.  
  
-   Výstupní adresář projektu definice návrháře.  
  
-   Umístění textového souboru šablony.  
  
 DslTextTransform.cmd zpracuje zadaný textový soubor šablony pomocí procesory direktiv výchozí a sestavení. Pokud vytvoříte vlastní procesory direktiv, můžete vytvořit vlastní dávkový soubor, který volá TextTransform.exe. V tento dávkový soubor můžete zadat vaše sestavení a přidružené vlastní procesory direktiv.