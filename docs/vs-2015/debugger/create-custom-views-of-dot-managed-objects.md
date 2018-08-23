---
title: Vytváření vlastních zobrazení spravovaných objektů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.data.elements
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- data types [C#], custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
caps.latest.revision: 37
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a84802e3b4e3c32f917dba56fce95268e39cd4bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632209"
---
# <a name="create-custom-views-of-managed-objects"></a>Vytváření vlastních zobrazení spravovaných objektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vytváření vlastních zobrazení spravovaných objektů](https://docs.microsoft.com/visualstudio/debugger/create-custom-views-of-dot-managed-objects).  
  
Můžete přizpůsobit tak, jak Visual Studio zobrazí datové typy v oknech proměnných ladicího programu.  
  
## <a name="attributes"></a>Atributy  
 V jazyce C# a Visual Basic, přidáte rozšíření pro vlastní data s využitím <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, a <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 V [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] kódu Visual Basic nepodporuje atribut DebuggerBrowsable. Toto omezení neplatí v novějších verzích rozhraní .NET Framework.  
  
## <a name="visualizers"></a>Vizualizéry  
 Můžete napsat vizualizéru pro zobrazení libovolného typu spravovaná data. Další informace najdete v tématu [postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Nativní kód  
 Pro nativní kód můžete přidat vlastní datový typ rozšíření do autoexp.dat – soubor, který je umístěn v adresáři 11.0\Common7\Packages\Debugger Program Files\Microsoft Visual Studio. Pokyny, jak psát `autoexp` pravidla jsou umístěny v samotném souboru.  
  
> [!CAUTION]
>  Struktura tohoto souboru a syntaxe pravidla autoexp může změnit v každé verzi sady Visual Studio na další.  
  
 Nativní typ zobrazení můžete přizpůsobit také napsáním výrazu chyba při vyhodnocování doplňku. Další informace najdete v tématu [EEAddIn vzorku: ladění Expression Evaluator Add-In](http://msdn.microsoft.com/en-us/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Rozšíření ladění pomocí atributů zobrazení ladicího programu](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)



