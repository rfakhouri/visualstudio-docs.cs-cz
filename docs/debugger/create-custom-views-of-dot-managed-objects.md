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
ms.openlocfilehash: 911f0423184f22919be016691b9333b2f62d1b61
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744791"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>Vytváření vlastních zobrazení objektů (C#, Visual Basic, C++)
Můžete přizpůsobit tak, jak Visual Studio zobrazí datové typy v oknech proměnných ladicího programu.

## <a name="native-code"></a>Nativní kód

Pro C++ kódu, můžete přidat vlastní datový typ rozšíření pomocí rozhraní Natvis, jak je popsáno v [vytváření vlastních zobrazení C++ objektů v ladicím programu](/visualstudio/debugger/create-custom-views-of-native-objects). Pro C++/rozhraní příkazového řádku kódu, můžete také použít atributy, které jsou zde popsané v tomto článku.

## <a name="attributes"></a>Atributy

V C#, Visual Basic a C++ (C++vyhodnocovací jenom kód), přidáte rozšíření pro vlastní data s využitím <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, a <xref:System.Diagnostics.DebuggerBrowsableAttribute>.

V kódu rozhraní .NET Framework 2.0 Visual Basic nepodporuje atribut DebuggerBrowsable. Toto omezení neplatí v novějších verzích rozhraní .NET Framework.

## <a name="visualizers"></a>Vizualizéry

Můžete napsat vizualizéru pro zobrazení libovolného typu spravovaná data. Další informace najdete v tématu [jak: Zápis Vizualizéru](/visualstudio/debugger/create-custom-visualizers-of-data).

## <a name="see-also"></a>Viz také

- [Ladicí program říct, co se má zobrazit, pomocí atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)
- [Ladicí program zjistit, jaký typ zobrazíte používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)
- [Okna Kukátko a Rychlé kukátko](../debugger/watch-and-quickwatch-windows.md)
- [Rozšíření ladění pomocí atributů zobrazení ladicího programu](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)