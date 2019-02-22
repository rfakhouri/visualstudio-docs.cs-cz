---
title: Vytváření vlastních zobrazení objektů | Dokumentace Microsoftu
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 748305683ad8f874c985e2599028152d608ccc84
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56597415"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>Vytváření vlastních zobrazení objektů (C#, Visual Basic, C++)
Můžete přizpůsobit tak, jak Visual Studio zobrazí datové typy v oknech proměnných ladicího programu.

## <a name="native-code"></a>Nativní kód

Pro kód jazyka C++, můžete přidat vlastní datový typ rozšíření pomocí rozhraní Natvis, jak je popsáno v [vytváření vlastních pohledů nativních objektů v ladicím programu](/visualstudio/debugger/create-custom-views-of-native-objects). Pro C + +/ CLI kódu, můžete také použít atributy, které jsou zde popsané v tomto článku.

## <a name="attributes"></a>Atributy

V C#, Visual Basic a C++ (C + +/ CLI kódu pouze), přidáte rozšíření pro vlastní data s využitím <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, a <xref:System.Diagnostics.DebuggerBrowsableAttribute>.

V [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] kódu Visual Basic nepodporuje atribut DebuggerBrowsable. Toto omezení neplatí v novějších verzích rozhraní .NET Framework.

## <a name="visualizers"></a>Vizualizéry

Můžete napsat vizualizéru pro zobrazení libovolného typu spravovaná data. Další informace najdete v tématu [jak: Zápis Vizualizéru](/visualstudio/debugger/create-custom-visualizers-of-data).

## <a name="see-also"></a>Viz také

- [Používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)
- [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)
- [Okna Kukátko a Rychlé kukátko](../debugger/watch-and-quickwatch-windows.md)
- [Rozšíření ladění pomocí atributů zobrazení ladicího programu](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)