---
title: Operátory rozšířeného vyhledávání ve vyhledávacích výrazech | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Help Viewer 2.0, searching for keywords
- Help Viewer 2.0, searching code
- Help Viewer 2.0, searching code by programming language
- Help Viewer 2.0, searching titles
- searching code [Help Viewer 2.0]
- searching titles [Help Viewer 2.0]
ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9c2b8df3878f67207b22127881722aedd8caae8e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775571"
---
# <a name="advanced-search-operators-in-search-expressions"></a>Operátory rozšířeného vyhledávání ve vyhledávacích výrazech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí operátory rozšířeného vyhledávání můžete upřesnit vyhledávání pro obsah tak, že vytvoříte složitější hledaných výrazů od těch jednodušší. Jak ukazuje následující tabulka tyto operátory omezení kontext, ve kterém se spouští dotaz.  
  
> [!WARNING]
>  Je nutné zadat operátory rozšířeného vyhledávání konečné dvojtečku žádné použité mezeru před dvojtečku pro vyhledávací web rozpoznány.  
  
|K vyhledání|Použití|Příklad|Výsledek|  
|-------------------|---------|-------------|------------|  
|Výraz v název tématu|Název:|Title: binaryreader|Témata, které obsahují "binaryreader" v názvech.|  
|Termín v příkladu kódu|Kód:|kód: readdouble|Témata, které obsahují "readdouble" v příkladu kódu.|  
|Výraz v příklad konkrétní programovací jazyk|vb: kód:|code:vb:string|Témata, které obsahují "string" v příkladu jazyka Visual Basic.|  
|Téma, které souvisí s klíčovým slovem konkrétního indexu|klíčové slovo:|klíčové slovo: readbyte|Témata, které jsou spojeny s klíčovým slovem "readbyte" index.|  
  
 Můžete použít kód: operátor hledání obsahu o všech různých programovacích jazyků, ale vrátí výsledky pouze pro obsah, který je označen s konkrétní programovací jazyk. V následující tabulce jsou uvedeny programovacích jazyků, které podporuje tento operátor:  
  
|Programovací jazyk|Použití|  
|--------------------------|---------|  
|Visual Basic|kód jazyka Visual Basic:<br /><br /> or<br /><br /> code:visualbasic|  
|C#|code:c#<br /><br /> or<br /><br /> code:csharp|  
|C++|code:cpp<br /><br /> or<br /><br /> kód: c ++<br /><br /> or<br /><br /> code:cplusplus|  
|F#|kód: f #<br /><br /> or<br /><br /> kód: fsharp|  
|JavaScript|kód: jazyka javascript<br /><br /> or<br /><br /> kód: js|  
|XAML|kód: xaml|  
  
## <a name="see-also"></a>Viz také  
 [Logické operátory ve vyhledávacích výrazech](../ide/logical-operators-in-search-expressions.md)   
 [Tipy pro fulltextové vyhledávání](../ide/full-text-search-tips.md)
