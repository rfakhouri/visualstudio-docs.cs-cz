---
title: Modul Common Language Runtime a vyhodnocení výrazu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, and common language runtime
ms.assetid: b36c1eb5-1aaf-48a6-b287-ee7a273d2b1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 370b7963c71b74674c7d323a5fa1c2650d3f08d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="common-language-runtime-and-expression-evaluation"></a>Modul Common Language Runtime a vyhodnocení výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Kompilátory, například Visual Basic a C# (vyslovováno C ostré), která cílí na Common Language Runtime (CLR), vytvořit Microsoft zprostředkující jazyk (MSIL), která se později zkompilovat do nativního kódu. Modul CLR poskytuje modul ladění (DE) k ladění výsledný kód. Pokud budete chtít integrovat programovacího jazyka proprietární do prostředí Visual Studio IDE, můžete zvolit zkompilovat do MSIL a proto nebudete muset psát vlastní DE. Ale budete muset zápis vyhodnocení výrazu (EE), který je schopen vyhodnocení výrazů v kontextu programovacího jazyka.  
  
## <a name="discussion"></a>Diskusní  
 Výrazy jazyka pro počítač jsou obecně analyzovat k vytvoření sadu datové objekty a sadu operátory používá k manipulaci s nimi. Výraz, který "A + B" může analyzovat použít operátor sčítání (+) na data například objekty "A" a "B" může být výsledkem jiného datového objektu. Celkový počet sadu datových objektů, operátory a jejich přidružení jsou nejčastěji vyjádřené v programu strom, s operátory v uzlu stromu a datové objekty v větve. Výraz, který má rozdělit do stromu formuláře se často nazývá analyzovaný strom.  
  
 Po analýze výraz symbol zprostředkovatele (SP) se nazývá vyhodnotit každý datový objekt. Například, pokud "A" je definovaný v více než jedna metoda a potom na otázku "Které A?" musí být zodpovězena, než lze zjistit hodnotu A. Odpověď vrácená SP je něco podobného jako "Třetí položka páté rámec zásobníku" nebo "A, který je 50 bajty za spuštění statické paměti přidělené této metody."  
  
 Kromě vytváření MSIL pro této aplikace, kompilátory CLR můžete také vytvořit velmi popisné informace pro ladění, která jsou zapsána do souboru databáze programu (.pdb). Tak dlouho, dokud kompilátoru jazyka nechráněný vytváří informace o ladění do stejný formát jako kompilátory CLR, modul CLR SP je dokáže zjistit, že tohoto jazyka s názvem datových objektů. Po objekt s názvem dat byla zjištěna, EE používá objekt vazač přiřadit (nebo vytvořit vazbu) datový objekt na oblast paměti, který uchovává hodnotu tohoto objektu. DE potom můžete získat nebo nastavit nové hodnoty pro datový objekt.  
  
 Vlastní kompilátoru může poskytnout CLR ladicí informace voláním `ISymbolWriter` rozhraní (která je definována v rozhraní .NET Framework v oboru názvů `System.Diagnostics.SymbolStore`). Kompilování k MSIL a zápis informace o ladění tato rozhraní, můžete použít vlastní kompilátoru CLR DE a služeb. To výrazně zjednodušuje integraci vlastní jazyk do prostředí Visual Studio IDE.  
  
 Když CLR DE volá proprietární EE k vyhodnocení výrazu, DE poskytuje EE s rozhraními SP a objekt vazače. Zápis modulu prostředky na základě CLR ladění z toho důvodu je nezbytné pouze k implementaci rozhraní vyhodnocování odpovídající výraz; modul CLR má na starosti vazby a symbol zpracování za vás.  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)