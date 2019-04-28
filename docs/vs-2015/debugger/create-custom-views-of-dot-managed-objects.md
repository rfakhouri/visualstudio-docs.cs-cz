---
title: Vytváření vlastních zobrazení spravovaných objektů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fbbfbe17fa5dfb9a10f530981643be7a0042d6fc
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440454"
---
# <a name="create-custom-views-of-managed-objects"></a>Vytváření vlastních zobrazení spravovaných objektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete přizpůsobit tak, jak Visual Studio zobrazí datové typy v oknech proměnných ladicího programu.  
  
## <a name="attributes"></a>Atributy  
 V jazyce C# a Visual Basic, přidáte rozšíření pro vlastní data s využitím <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, a <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 V [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] kódu Visual Basic nepodporuje atribut DebuggerBrowsable. Toto omezení neplatí v novějších verzích rozhraní .NET Framework.  
  
## <a name="visualizers"></a>Vizualizéry  
 Můžete napsat vizualizéru pro zobrazení libovolného typu spravovaná data. Další informace najdete v tématu [jak: Zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Nativní kód  
 Pro nativní kód můžete přidat vlastní datový typ rozšíření do autoexp.dat – soubor, který je umístěn v adresáři 11.0\Common7\Packages\Debugger Program Files\Microsoft Visual Studio. Pokyny, jak psát `autoexp` pravidla jsou umístěny v samotném souboru.  
  
> [!CAUTION]
> Struktura tohoto souboru a syntaxe pravidla autoexp může změnit v každé verzi sady Visual Studio na další.  
  
 Nativní typ zobrazení můžete přizpůsobit také napsáním výrazu chyba při vyhodnocování doplňku. Další informace najdete v tématu [EEAddIn vzorku: Ladění Expression Evaluator Add-In](http://msdn.microsoft.com/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Rozšíření ladění pomocí atributů zobrazení ladicího programu](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)
