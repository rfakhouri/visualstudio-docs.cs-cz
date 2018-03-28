---
title: Nalezení potenciálních problémů pomocí analyzátorů mapy kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 228012039c360e362948d6566411cf05720627f0
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>Nalezení potenciálních problémů pomocí analyzátorů mapy kódu
Spustili analyzátorů mapy kódu, který vám pomůže identifikovat kód, který může být příliš složité nebo která potřebujete zlepšování. Například můžete použít tyto analyzátorů:  

|**Najít kód, který má**|**Prozkoumat tyto oblasti zobrazíte zda**|  
|-------------------------------|--------------------------------------------|  
|Smyčky nebo cyklické závislosti|Můžete je zjednodušit a zvažte, zda lze rozdělit tyto cykly.|  
|Příliš velký počet závislostí|Provádění příliš mnoho funkcí nebo zjistit dopad změny těchto oblastí. Minimální počet závislostí se zobrazí mapě kódu ve správném formátu. Abyste mohli snadněji spravovat, změnit, testování a znovu použít, zvažte, jestli Refaktorovat těchto oblastem tak, aby se více jasně definované, nebo jestli můžete sloučit kód, který provádí podobné funkce jako kód.|  
|Žádné závislosti|Jsou zapotřebí nebo jestli byste měli odebrat tento kód.|  

## <a name="analyze-code-maps"></a>Analýza mapy kódu  

1.  Na panelu nástrojů mapy zvolte **rozložení**, **analyzátorů**a pak analyzátor, který chcete spustit:  

    |**Analyzátor**|**K identifikaci uzlů,**|  
    |------------------|--------------------------------|  
    |**Analyzátor cyklické odkazy**|Cyklické závislosti jsou na sobě navzájem. **Poznámka:** cyklické závislosti, které jsou v **obecné typy** skupiny nejsou zobrazeny na mapě. když rozbalte skupinu.|  
    |**Najít analyzátor rozbočovače**|Jsou v horní 25 % vysoce připojené uzlů<br /><br /> **Chcete-li skrýt všechny uzly na mapě**<br /><br /> -Otevřete místní nabídky pro mapu, zvolte **Upřesnit**, **vyberte**, **skrýt nezaškrtnuté**.<br />     Mapy skryje nezaškrtnuté uzlů a nástroje analyzer identifikuje nové uzly jako rozbočovače.|  
    |**Analyzátor neregistrované uzly**|Nemají odkazy z jiných uzlů. **Upozornění:** ověření jednotlivých případech před za předpokladu, že kód nepoužívá. Určité závislosti, jako je například XAML závislosti a závislosti běhu nebyl nalezen staticky v kódu.|  

 Analyzátorů mapy kódu se bude nadále spouštět po jejich použití. Pokud změníte mapy, všechny použité analyzátorů bude automaticky znovu zpracovat aktualizovanou mapy. Zastaví analyzátor, na panelu nástrojů mapy, zvolte **rozložení**, **analyzátorů**. Vypněte vybrané analyzátor.  

> [!TIP]
>  Pokud máte velké mapy, spuštění analyzátor může způsobit nedostatku paměti výjimky. Pokud k tomu dojde, upravte mapování omezit její obor nebo vygenerovat menší a pak spustit Analyzátor.  

## <a name="see-also"></a>Viz také  
 [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)   
 [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
