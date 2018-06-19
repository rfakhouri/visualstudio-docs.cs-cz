---
title: Kompilátoru platformu .NET (&quot;Roslyn&quot;) rozšiřitelnost | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09287c48285bfcdc32b1a7d558d44f9d212f1b41
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126933"
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>Kompilátoru platformu .NET (&quot;Roslyn&quot;) rozšiřitelnosti
Zvláště základní kompilátoru platformy .NET ("Roslyn") je otevírání až kompilátory jazyka C# a Visual Basic a povolení nástrojů a vývojářům sdílet v kompilátory bohaté informace mají o programy. Nástrojů pro analýzu kódu zlepšení kvality kódu a kódu generátory podpory v vytváření aplikace. Jak lépe nástroje, musí na další a další znalostí hloubkové kód, který měl pouze kompilátory přístup. Namísto neprůhledného překladatelé (zdrojový kód v a kód objektu out) nabízejí kompilátory Roslyn rozhraní API, které můžete použít pro úlohy související s kódem v nástrojů a aplikací.  
  
 Nejlepší je, že kompilátory Roslyn, příslušných rozhraní API, ukázky a návody a skutečné nástroje postavená na tato rozhraní API jsou všechny plně open zdroje v [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn). Přejděte do operačních systémů lokality na další informace a začátek práce s Roslyn. Najdete odkazy na získejte nejnovější C# a VB funkce, které můžete použít jako koncový uživatel, jakož i odkazy na Začínáme jako nástroj Tvůrce využívají rozhraní API Roslyn.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme s analyzátory Roslyn](../extensibility/getting-started-with-roslyn-analyzers.md)