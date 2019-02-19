---
title: Logické operátory ve vyhledávacích výrazech | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Help Viewer 2.0, logical operators in search
- logical operators in search [Help Viewer 2.0]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 66d6aa6a11ef0ce308c5ba2b089aaa8170b6441f
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54760067"
---
# <a name="logical-operators-in-search-expressions"></a>Logické operátory ve vyhledávacích výrazech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí logických operátorů, můžete upřesnit vyhledávání pro obsah tak, že vytvoříte složitější hledaných výrazů od těch jednodušší. Jako v následující tabulce jsou uvedeny, logické operátory určují, jak více podmínek vyhledávání by měly být kombinované vyhledávacího dotazu.  
  
> [!IMPORTANT]
>  Logické operátory je nutné zadat velkými písmeny pro vyhledávače rozpoznány.  
  
|K vyhledání|Použití|Příklad|Výsledek|  
|-------------------|---------|-------------|------------|  
|Oba výrazy ve stejném tématu|AND|DIB a palety|Témata, které obsahují "dib" a "palety".|  
|Buď výraz v tématu|NEBO|rastrové vektoru OR|Témata, které obsahují "rastrové" nebo "vektorové".|  
|První výraz bez druhý výraz ve stejném tématu|NOT|"operační systém" není DOS|Témata, které obsahují "operační systém", ale ne "DOS".|  
|Oba výrazy blízko sebe v tématu|V BLÍZKOSTI|uživatel TÉMĚŘ jádra|Témata, která obsahují "user" v blízkosti "jádra".|  
  
## <a name="see-also"></a>Viz také  
 [Tipy pro fulltextové vyhledávání](../ide/full-text-search-tips.md)   
 [Vyhledávání informací](../ide/locate-information.md)
