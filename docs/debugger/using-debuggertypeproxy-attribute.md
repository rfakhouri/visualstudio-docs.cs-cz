---
title: Používání atributu DebuggerTypeProxy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 89a3ea96e3ceb473db753a0e238a75d5cdd0e106
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="using-debuggertypeproxy-attribute"></a>Používání atributu DebuggerTypeProxy
<xref:System.Diagnostics.DebuggerTypeProxyAttribute> Určuje server proxy nebo stand-in, typu a změny, které způsob typ se zobrazí v ladicího programu. Při zobrazení proměnné, která má proxy server proxy serveru znamená původní typu v **zobrazení**. V okně proměnné ladicí program se zobrazí pouze veřejné členy typ proxy. Soukromé členy nejsou zobrazeny.  
  
 Tento atribut lze použít:  
  
-   Struktury  
  
-   Třídy  
  
-   Sestavení  
  
 Typ třídy proxy musí mít konstruktor, který používá argument s typem, který nahradí proxy serveru. Ladicí program vytvoří novou instanci třídy proxy pokaždé, když bude potřebovat zobrazit proměnné cílového typu. To může mít vliv na výkon. V důsledku toho neměli dělat žádné další práci v konstruktoru, než je nezbytně nutné.  
  
 Chcete-li minimalizovat penalizacím výkonu, vyhodnocovací filtr výrazů není zkontrolujte atributy na proxy zobrazení typu Pokud typ je rozšířena uživatel kliknutím + symbol v okně ladicího programu nebo použití <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Proto by nemělo umístit atributy na vlastní typ zobrazení. Atributy lze a je třeba používat v těle typu zobrazení.  
  
 Je vhodné pro typ proxy být privátní vnořené třídy v rámci třídy, které cíle atributů. To umožňuje snadno přístup vnitřní členy.  
  
 Pokud <xref:System.Diagnostics.DebuggerTypeProxyAttribute> se používá na úrovni sestavení `Target` parametr určuje typ, který nahradí proxy serveru.  
  
 Příklad použití tohoto atributu spolu s <xref:System.Diagnostics.DebuggerDisplayAttribute> a <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, najdete v části[používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Pomocí debuggertypeproxy – obecné typy  
 Podpora je omezena. Pro jazyk C# `DebuggerTypeProxy` podporuje pouze otevřete typy. Otevřený typ, označované taky jako typ unconstructed je obecný typ, který nebyla inicializována s argumenty jeho parametrů typu. Uzavřené typy, označované taky jako sestavené typy nejsou podporovány.  
  
 Syntaxe pro otevřený typ. vypadá takto:  
  
 `Namespace.TypeName<,>`  
  
 Pokud použijete obecného typu jako cíl v `DebuggerTypeProxy`, je nutné použít tuto syntaxi. `DebuggerTypeProxy` Mechanismus odvodí, že parametry typu za vás.  
  
 Další informace o typech otevřené a uzavřené v jazyce C# najdete v článku [specifikace jazyka C#](/dotnet/csharp/language-reference/language-specification), otevřete část 20.5.2 a uzavřen typy.  
  
 Visual Basic nemá otevřený typ syntaxe, nelze to samé v jazyce Visual Basic. Místo toho musíte použít řetězec reprezentující název otevřete typu.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
 [Vytváření vlastních pohledů .managed objektů](../debugger/create-custom-views-of-dot-managed-objects.md)   
 [Rozšíření ladění pomocí atributů zobrazení ladicího programu](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)