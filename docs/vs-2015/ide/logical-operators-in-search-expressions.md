---
title: Logické operátory ve vyhledávacích výrazech | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, logical operators in search
- logical operators in search [Help Viewer 2.0]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0cf55bbdc025b4aabd13f7ded72c2ea69386a61b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627673"
---
# <a name="logical-operators-in-search-expressions"></a>Logické operátory ve vyhledávacích výrazech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [logické operátory ve vyhledávacích výrazech](https://docs.microsoft.com/visualstudio/ide/logical-operators-in-search-expressions).  
  
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
 [Vyhledejte informace](../ide/locate-information.md)



