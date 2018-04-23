---
title: Vytváření vlastních pohledů spravované objekty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6be491a5c7a0ceb0ed536416cdd3b273f96b4bb1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="create-custom-views-of-managed-objects"></a>Vytvořit vlastní zobrazení spravovaných objektů
Můžete upravit způsob, jakým Visual Studio zobrazí datové typy v proměnnými ladicího programu.  
  
## <a name="attributes"></a>Atributy  
 V jazyce C# a Visual Basic, můžete přidat rozšíření pro vlastní data pomocí <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, a <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 V [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] kódu Visual Basic nepodporuje atribut DebuggerBrowsable. V novějších verzích rozhraní .NET Framework bylo toto omezení odstraněno.  
  
## <a name="visualizers"></a>Vizualizéry  
 Můžete napsat vizualizéru zobrazíte jakéhokoli spravované datového typu. Další informace najdete v tématu [postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Nativní kód  
 Pro nativní kód můžete přidat vlastní datový typ rozšíření do autoexp.dat – soubor, který je umístěný v adresáři 11.0\Common7\Packages\Debugger Program Files\Microsoft Visual Studio. Pokyny, jak napsat `autoexp` pravidla jsou umístěny v samotném souboru.  
  
> [!CAUTION]
>  Struktura tento soubor a syntaxe pravidla autoexp může změnit z jedné verze sady Visual Studio na další.  
  
 Nativní typ zobrazení můžete také přizpůsobit zápis vyhodnocování doplňku výraz. Další informace najdete v tématu [EEAddIn ukázka: ladění výraz vyhodnocování Add-In](http://msdn.microsoft.com/en-us/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Sledování a QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Rozšíření ladění pomocí atributů zobrazení ladicího programu](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)