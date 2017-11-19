---
title: "Glosář ladicího programu sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- glossary [Debugging SDK]
- debugging [Debugging SDK], glossary
ms.assetid: 4a2cfaab-1fbd-4a23-bd00-9ac4cc50d7fd
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c4b91633c94b899157cef5418be0ac8a4d784f1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-debugger-glossary"></a>Glosář ladicího programu sady Visual Studio
Toto jsou termínů používaných v [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladění SDK.  
  
## <a name="terms"></a>Podmínky  
 vázané Breakpoint –  
 Nastavit abstrakci pro zarážky v kódu. Existuje relace 1: 1 mezi vázané Breakpoint – a zarážek instrukce v datovém proudu kódu. Když kódu uvolní, může zrušit vazbu vázané zarážky.  
  
 příčiny  
 Poskytuje schopnost sledovat logický podproces provádění napříč více fyzických vláken, procesy a počítačů a rekonstrukci zásobníku volání této logické vlákna v libovolném časovém okamžiku v daném vláknu životnosti.  
  
 kontext kódu  
 Poskytuje abstrakci pozici v kódu ví, že modul ladění. Pro většinu běhu architektury kontext kódu se jedná o adresu v datovém proudu instrukce programu. Pro netradičních jazyky, ve kterých nemusí být reprezentován kód podle pokynů, může být reprezentován kontext kódu jiným způsobem.  
  
 cesta kódu  
 Představuje bod spouštění v kódu, kde je provedena větev nebo je provedeno volání funkce. Trasování zásobníku je v podstatě seznam cesty kódu volání funkce.  
  
 ladění modulu (DE)  
 Komponenta, která umožňuje ladění architektury běhu. Modul ladění funguje ve spojení s překladač nebo operačního systému a poskytuje ladění služby, jako je například spouštění řízení, zarážky a výraz vyhodnocení.  
  
 kontext dokumentu  
 Poskytuje abstrakci pozici ve zdrojovém dokumentu souboru ví, že modul ladění. Pro většinu jazyků je kontextu dokumentu pozici ve zdrojovém souboru. Pro netradičních jazyky, pro které nemusí být zdrojový soubor text, může být reprezentován kontextu dokumentu jiným způsobem. Viz také *pozice dokumentu*.  
  
 pozice dokumentu  
 Poskytuje abstrakci pozici ve zdrojovém souboru ví, že rozhraní IDE. Umístění dokumentu většiny jazyků, slouží jako zdrojový soubor. Pro netradičních jazyky může být reprezentován pozice dokumentu jinými způsoby. Viz také *kontextu dokumentu*.  
  
 Breakpoint – chyba  
 Abstrakci pro popisující chybu v čekající zarážky. K chybě zarážek může popisují chybu v umístění čekající zarážek výraz přidružený k čekající zarážek nebo Další informace, které brání čekající zarážek vazby do umístění kódu.  
  
 kontext vyhodnocení  
 Poskytuje abstrakci programovacím kontextu pro vyhodnocení výrazu. Kontext vyhodnocení je obvykle obor. Při provádění vyhodnocení výrazu v kontextu výrazu, poskytuje kontext Výraz pravidla rozsahu, které odpovídají jeho bod vytvoření. Například kontextu výraz, který je vytvořen v rámci zásobníku poskytne kontext pro vyhodnocení lokální proměnné, parametry metody, členy třídy (pokud existuje) a globální proměnné.  
  
 zachycené výjimky  
 Výjimka, která je zachycen modul ladění, i když žádná výjimka mechanismu pro zpracování v místě v aktuální rámec zásobníku.  
  
 JustMyCode  
 Základní informace o ladění pouze kód, který patří uživateli a ignoruje všechny zprostředkující kódu, například kód systému – přestože zdrojový kód je k dispozici pro tento kód systému.  
  
 čekající zarážek  
 Poskytuje abstrakci pro zarážky před, během a po kód je načíst a způsob, jak Virtualizovat zarážky. A čeká na zarážek:  
  
-   Obsahuje všechny informace potřebné k vytvoření vazby zarážku kód v jeden nebo více programů.  
  
-   Může vytvořit vazbu na několika místech kódu v jeden nebo více programů.  
  
-   Nikdy sváže samotný kód.  
  
 Načte každý kódu v době, pokud chcete zobrazit, pokud lze vázat se kontroluje všechny čekající zarážky v programu. Čekající zarážek říká, že je tak, aby obsahovala všechny vázané zarážky, které se váže.  
  
 zpracování  
 Fyzické Win32 proces. Proces může obsahovat více programů. Viz také *programu*.  
  
 program  
 Jeden obor názvů běžících v rámci konkrétní architektura běhu. Viz také *proces*.  
  
 Správce ladicí relace (SDM)  
 Spravuje libovolný počet modulů ladění ladění libovolný počet programy v několika procesů na libovolný počet počítačů. Na základní úrovni je SDM multiplexor modulů ladění. Kromě toho SDM poskytuje jednotný pohled na relaci ladění k prostředí IDE.  
  
 rámec zásobníku  
 Představuje stav výpočtu na určitého snímku a konkrétní úrovni volání vnořené funkce.  
  
 vlákno  
 Zobecněný představu o spuštění na základě zásobníku instrukce spuštěná alespoň jedné aplikace.  
  
 Breakpoint – upozornění  
 Abstrakci pro popisující upozornění v čekající zarážky. Upozornění zarážek popisuje důvod, proč nebyl čekající zarážek ještě vázána na umístění kódu. To může být, že kód nebyl dosud načtena pro popsaného čekající zarážek umístění, nebo z jiného důvodu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost ladicího programu sady Visual Studio](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)