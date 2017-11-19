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
ms.openlocfilehash: fd45a33b421e889b05fd78eceddc0b05126e4a21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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