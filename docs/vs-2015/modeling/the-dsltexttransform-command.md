---
title: Příkaz DslTextTransform | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8a565fa6226348a1fe1b6dcfcbb67f704e74abc8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670756"
---
# <a name="the-dsltexttransform-command"></a>Příkaz DslTextTransform
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [The příkaz DslTextTransform](https://docs.microsoft.com/visualstudio/modeling/the-dsltexttransform-command).  
  
DslTextTransform.cmd je skript, který volá TextTransform.exe a spustí pomocí běžné možnosti. DslTextTransformation.cmd můžete použít k automatizaci noční sestavení z vašeho [!INCLUDE[dsl](../includes/dsl-md.md)] projekty. Další informace najdete v tématu [generování souborů pomocí nástroje TextTransform](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd se nachází v následujícím adresáři:  
  
 **\<Visual Studio SDK Instalační_cesta > \VisualStudioIntegration\Tools\Bin**  
  
 Jako vstup pro DslTextTransform.cmd lze zadat následující argumenty:  
  
-   Výstupní adresář projektu s modelem domény.  
  
-   Výstupní adresář projektu definice návrháře.  
  
-   Umístění souboru textové šablony.  
  
 DslTextTransform.cmd zpracovává zadaný textový soubor šablony pomocí procesorů pro direktivy výchozí a sestavení. Pokud vytvoříte vlastní procesory direktiv, můžete vytvořit vlastní dávkový soubor, který volá TextTransform.exe. V tomto souboru služby batch můžete zadat sestavení a přidružené vlastní procesory direktiv.



