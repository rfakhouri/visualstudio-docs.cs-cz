---
redirect_url: /visualstudio/ide/logical-operators-in-search-expressions
ms.openlocfilehash: fe896af873197c95a4b226396e0b6333fdc40cfa
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
Title: "Pokročilí operátoři vyhledávání ve vyhledávacích výrazech | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 06/02/2017":" "ms.suite:" "ms.technology: 
  - ms.tgt_pltfrm "vs Prohlížeč nápovědy": "" ms.topic: "článku" helpviewer_keywords: 
  - "Help Viewer, hledání klíčových slov"
  - "Help Viewer, hledání kódu"
  - "Help Viewer, hledání kódu podle programovacího jazyka"
  - "Help Viewer, hledání nadpisů"
  - "hledání kódu [Help Viewer]"
  - "hledání nadpisů [Help Viewer]" ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e caps.latest.revision: 9 Autor: ms.author "gewarren": "gewarren" správce: ghogen
---
# <a name="advanced-search-operators-in-search-expressions"></a>Operátory rozšířeného vyhledávání ve vyhledávacích výrazech
Pomocí operátory rozšířeného vyhledávání v okně nápovědy, můžete upřesněte hledání obsahu zadáním kde v tématu hledání hledaný termín. Následující tabulka popisuje čtyři operátory k dispozici rozšířené vyhledávání.

|K vyhledání|Použití|Příklad|Výsledek|  
|-------------------|---------|-------------|------------|  
|Termín v název tématu|Název:|Title: binaryreader|Témata, které obsahují "binaryreader" v jejich názvy.|  
|Termín v příklad kódu|Kód:|kód: readdouble|Témata, které obsahují "readdouble" v příkladu kódu.|  
|Termín v Příkladem konkrétní programovací jazyk|vb: kód:|kód: vb:string|Témata obsahující "řetězec v příklad kódu jazyka Visual Basic.|  
|Téma, které souvisí s konkrétní index klíčové slovo|– klíčové slovo:|– klíčové slovo: readbyte|Témata, které jsou spojeny s klíčovým slovem "readbyte" index.|  

> [!WARNING]
>  Je nutné zadat operátory rozšířeného vyhledávání s posledním dvojtečkou a žádné použité místo před dvojtečkou pro vyhledávacího webu rozpoznány.    

## <a name="programming-languages-for-code-examples"></a>Programovací jazyky pro příklady kódu
Můžete použít kód: operátor hledání obsahu o všech několik programovacích jazyků, ale vrátí výsledky pouze pro obsah, který je označen s popiskem programovací jazyk. Příklady pro konkrétní programovací languge vrátit, použijte jednu z následujících hodnot programovací jazyk:  

|Programovací jazyk|Syntaxe vyhledávání – operátor|  
|--------------------|---------|  
|Visual Basic|kód jazyka Visual Basic:<br/>kód: visualbasic|  
|C#|kód: c#<br/>kód: csharp|  
|C++|kód: cpp<br/>kód: c ++<br/>kód: cplusplus|  
|F#|kód: f #<br/>kód: fsharp|  
|JavaScript|kód: javascript<br/>kód: js|  
|XAML|kód: xaml|
