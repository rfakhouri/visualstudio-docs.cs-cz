---
title: "Kompilátoru platformu .NET (&quot;Roslyn&quot;) rozšiřitelnost | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f9811440146e1d758158a64fd227ba0a2c2e1e4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>Kompilátoru platformu .NET (&quot;Roslyn&quot;) rozšiřitelnosti
Zvláště základní kompilátoru platformy .NET ("Roslyn") je otevírání až kompilátory jazyka C# a Visual Basic a povolení nástrojů a vývojářům sdílet v kompilátory bohaté informace mají o programy. Nástrojů pro analýzu kódu zlepšení kvality kódu a kódu generátory podpory v vytváření aplikace. Jak lépe nástroje, musí na další a další znalostí hloubkové kód, který měl pouze kompilátory přístup. Namísto neprůhledného překladatelé (zdrojový kód v a kód objektu out) nabízejí kompilátory Roslyn rozhraní API, které můžete použít pro úlohy související s kódem v nástrojů a aplikací.  
  
 Nejlepší je, že kompilátory Roslyn, příslušných rozhraní API, ukázky a návody a skutečné nástroje postavená na tato rozhraní API jsou všechny plně open zdroje v [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn). Přejděte do operačních systémů lokality na další informace a začátek práce s Roslyn. Najdete odkazy na získejte nejnovější C# a VB funkce, které můžete použít jako koncový uživatel, jakož i odkazy na Začínáme jako nástroj Tvůrce využívají rozhraní API Roslyn.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme s Roslyn analyzátory](../extensibility/getting-started-with-roslyn-analyzers.md)