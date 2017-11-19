---
title: "Logické operátory a pokročilí operátoři ve vyhledávání výrazy | Microsoft Docs"
ms.custom: 
ms.date: 11/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3378a554a9e576bde011a70916c48597218bb512
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Rozšířené a logické operátory ve vyhledávacích výrazech
Logické operátory a operátory rozšířeného vyhledávání můžete použít upřesněte hledání obsahu nápovědy v Help Viewer.

## <a name="logical-operators"></a>Logické operátory
Logické operátory určit, jak více podmínek vyhledávání by měla být kombinovány v vyhledávací dotaz. Následující tabulka uvádí logických operátorů AND, OR a není a v BLÍZKOSTI.
  
|K vyhledání|Použití|Příklad|Výsledek|  
|-------------------|---------|-------------|------------|  
|Oba termíny ve stejném článku|AND|DIB a palety|Témata, které obsahují "dib" a "palety".|  
|Buď termín v článku|NEBO|rastrové nebo vektoru|Témata, které obsahují "rastrových" nebo "vector".|  
|První výraz bez druhý výraz ve stejném článku|NENÍ|"operační systém" není DOS|Témata, které obsahují "operační systém", ale ne "DOS".|  
|Obě podmínky, zavřete společně v článku|V BLÍZKOSTI|uživatel TÉMĚŘ jádra|Témata, které obsahují "user" v blízkosti "jádra".|  
  
> [!IMPORTANT]
> Logické operátory je nutné zadat velkými písmeny pro vyhledávací rozpoznány.

## <a name="advanced-operators"></a>Pokročilí operátoři
Operátory rozšířeného vyhledávání upřesněte hledání obsahu zadáním kde v článku hledání hledaný termín. Následující tabulka popisuje čtyři operátory k dispozici rozšířené vyhledávání.

|K vyhledání|Použití|Příklad|Výsledek|  
|-------------------|---------|-------------|------------|  
|Termín v název článku|Název:|Title: binaryreader|Témata, které obsahují "binaryreader" v jejich názvy.|  
|Termín v příklad kódu|Kód:|kód: readdouble|Témata, které obsahují "readdouble" v příkladu kódu.|  
|Termín v Příkladem konkrétní programovací jazyk|vb: kód:|kód: vb:string|Témata obsahující "řetězec v příklad kódu jazyka Visual Basic.|  
|Článek, který je přidružen konkrétní index klíčové slovo|– klíčové slovo:|– klíčové slovo: readbyte|Témata, které jsou spojeny s klíčovým slovem "readbyte" index.|  

> [!IMPORTANT]
> Je nutné zadat operátory rozšířeného vyhledávání s posledním dvojtečkou a žádné použité místo před dvojtečkou pro vyhledávacího webu rozpoznány.    

### <a name="programming-languages-for-code-examples"></a>Programovací jazyky pro příklady kódu
Můžete použít **kód:** operátor hledání obsahu o všech několik programovacích jazyků. Vrátí příklady pro konkrétní programovací jazyk, použijte jednu z následujících hodnot programovací jazyk:  

|Programovací jazyk|Syntaxe vyhledávání – operátor|  
|--------------------|---------|  
|Visual Basic|kód jazyka Visual Basic:<br/>kód: visualbasic|  
|C#|kód: c#<br/>kód: csharp|  
|C++|kód: cpp<br/>kód: c ++<br/>kód: cplusplus|  
|F#|kód: f #<br/>kód: fsharp|  
|JavaScript|kód: javascript<br/>kód: js|  
|XAML|kód: xaml|

> [!NOTE]
> **Kód:** operátor vyhledá pouze obsah, který je označen s popiskem programovací jazyk, a obsah, který je obecně označeny jako kód. 
  
## <a name="see"></a>Další informace naleznete v tématu 
[Postupy: vyhledávání témat](how-to-search-for-topics.md)  
[Microsoft Help Viewer](microsoft-help-viewer.md)