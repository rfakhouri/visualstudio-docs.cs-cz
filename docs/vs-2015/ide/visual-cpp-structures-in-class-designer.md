---
title: Struktury jazyka Visual C++ v Návrháři tříd | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 19ffa241fdc1f58500c7065e2cee2a33340e33f8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423303"
---
# <a name="visual-c-structures-in-class-designer"></a>Struktury jazyka Visual C++ v návrháři tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Návrhář tříd podporuje C++ struktur, které jsou deklarovány pomocí klíčového slova `struct`. Tady je příklad:  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 Další informace o používání `struct` zadejte naleznete v tématu [struktura](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6).  
  
 Tvar struktury C++ v diagramu třídy vypadá a funguje jako tvar třídy, s tím rozdílem, že načte popisek **struktura** a má hranaté rohy místo zaoblené rohy.  
  
|Element kódu|Zobrazení návrháře tříd|  
|------------------|-------------------------|  
|`struct StructureName {};`|**%{Structurename/**<br /><br /> Struktura|  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Třídy a struktury](http://msdn.microsoft.com/library/516dd496-13fb-4f17-845a-e9ca45437873)   
 [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6)
