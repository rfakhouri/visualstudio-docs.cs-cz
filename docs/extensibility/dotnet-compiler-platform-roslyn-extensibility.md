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
ms.workload: vssdk
ms.openlocfilehash: b292593c6a6c426bb184acd67a920b5e76e3a51f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>Kompilátoru platformu .NET (&quot;Roslyn&quot;) rozšiřitelnosti
Zvláště základní kompilátoru platformy .NET ("Roslyn") je otevírání až kompilátory jazyka C# a Visual Basic a povolení nástrojů a vývojářům sdílet v kompilátory bohaté informace mají o programy. Nástrojů pro analýzu kódu zlepšení kvality kódu a kódu generátory podpory v vytváření aplikace. Jak lépe nástroje, musí na další a další znalostí hloubkové kód, který měl pouze kompilátory přístup. Namísto neprůhledného překladatelé (zdrojový kód v a kód objektu out) nabízejí kompilátory Roslyn rozhraní API, které můžete použít pro úlohy související s kódem v nástrojů a aplikací.  
  
 Nejlepší je, že kompilátory Roslyn, příslušných rozhraní API, ukázky a návody a skutečné nástroje postavená na tato rozhraní API jsou všechny plně open zdroje v [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn). Přejděte do operačních systémů lokality na další informace a začátek práce s Roslyn. Najdete odkazy na získejte nejnovější C# a VB funkce, které můžete použít jako koncový uživatel, jakož i odkazy na Začínáme jako nástroj Tvůrce využívají rozhraní API Roslyn.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme s analyzátory Roslyn](../extensibility/getting-started-with-roslyn-analyzers.md)