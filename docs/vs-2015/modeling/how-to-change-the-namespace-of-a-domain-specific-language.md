---
title: 'Postupy: Změnit Namespace jazyka specifického pro doménu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e86fa8f220cdd31beae12e050a1cbaa592624a74
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65690568"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Postupy: Změna oboru názvů jazyka specifického pro doménu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete změnit obor názvů jazyka specifického pro doménu. Je nutné provést změny v **Průzkumník DSL**ve vlastnostech projektu balíček Dsl a v informacích o sestavení.  
  
### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Chcete-li změnit obor názvů jazyka specifického pro doménu  
  
1. V **Průzkumník DSL**, klikněte na tlačítko **Dsl** uzlu.  
  
2. V **vlastnosti** okno Změnit **Namespace** vlastnost.  
  
3. Uložte řešení a transformaci šablon.  
  
4. Na **projektu** nabídky, klikněte na tlačítko **Dsl vlastnosti**.  
  
     Zobrazí vlastnosti pro váš projekt.  
  
5. Klikněte na tlačítko **aplikace** kartu.  
  
6. Změnit **výchozí obor názvů** vlastnost na nový název oboru názvů.  
  
7. Pokud chcete změnit název sestavení, změňte **vlastnost názvu sestavení.**  
  
8. Pokud jste změnili název sestavení, otevřete DslPackage\Package.tt a aktualizovat tento řádek:  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. Pokud jste napsali žádný vlastní kód, ujistěte se, že chcete-li změnit odkazy na obor názvů a třídy v souboru kódu.  
  
10. Resetujte Visual Studio experimentální instanci aplikace.  
  
    1. Odstranit **\Users\\**_{name}_**\AppData\Local\Microsoft\VisualStudio\\\*Exp**  
  
    2. V Windows **Start** nabídce zvolte **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**, **resetovat Experimentální instanci**.  
  
11. Na **sestavení** nabídce zvolte **znovu sestavit řešení**.  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
