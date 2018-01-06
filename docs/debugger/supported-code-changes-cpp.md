---
title: "Podporované změny kódu (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue, limitations
- supported code changes
- object files, limitations of Edit and Continue
- C# language, supported code changes
- coding, supported code changes
- resource files, limitations of Edit and Continue
- code changes, handling in Edit and Continue
- what's new [C#], supported code changes
- code changes
ms.assetid: f5754363-8a56-417b-b904-b05d9dd26d03
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b3ced43c776cc948467d68b2112fb808dd2a48c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="supported-code-changes-c"></a>Podporované změny kódu (C++)
Upravit a pokračovat jazyka Visual C++ zpracovává většinu typů změn kódu. Některé změny však nelze použít při spuštění programu. Pokud chcete tyto změny použít, musíte zastavit provádění a vytvořit novou verzi kód.  
  
 V tématu [upravit a pokračovat (Visual C++)](../debugger/edit-and-continue-visual-cpp.md) informace o práci s upravit a pokračovat jazyka C++ v sadě Visual Studio.  
  
##  <a name="BKMK_Unsupported_changes"></a>Nepodporované změny  
 Následující změny C/C++ nejde použít během relace ladění:  
  
-   Většinu změn dat globální nebo statické.  
  
-   Změny spustitelné soubory, které jsou zkopírovány z jiného počítače a Nevytvořen místně.  
  
-   Změny na datový typ, které mají vliv na rozložení objektu, například data členové třídy.  
  
-   Přidání víc než 64 kB nový kód nebo data.  
  
-   Přidání proměnné, které vyžadují konstruktor v okamžiku před ukazatel instrukce.  
  
-   Změny, které mají vliv kód, který vyžaduje spuštění inicializace.  
  
-   Přidání obslužné rutiny výjimek, v některých případech.  
  
-   Změny zdrojových souborů.  
  
-   Změny kódu v souborech jen pro čtení.  
  
-   Změny kódu bez odpovídající soubor PDB.  
  
-   Změny kódu, který nemá soubor objekt.  
  
 Pokud provedete jednu z těchto změn a potom se pokusíte použít změny kódu, chybě nebo upozornění se zobrazí v **výstup** okno.  
  
-   Upravit a pokračovat v aktualizaci statických knihoven. Pokud provedete změny v statickou knihovnu, provádění pokračuje v předchozí verzi a žádné upozornění.  
  
##  <a name="BKMK_Unsupported_scenarios"></a>Nepodporované scénáře  
 Upravit a pokračovat pro C/C++ není k dispozici v následujících scénářích ladění:  
  
-   Ladění nativní aplikace, kompilovat s [/Zo (vylepšit optimalizované ladění)](/cpp/build/reference/zo-enhance-optimized-debugging)  
  
-   Ve verzích sady Visual Studio předchozí Visual Studio 2015 Update 1, ladění aplikace UWP nebo součástí. Od verze Visual Studio 2015 Update 1, můžete upravit a pokračovat v UWP C++ aplikací a aplikací rozhraní DirectX, protože teď podporuje `/ZI` přepínače kompilátoru s `/bigobj` přepínače. Můžete také upravit a pokračovat s binárními soubory kompilovat s `/FASTLINK` přepínače.  
  
-   Ladění na Windows 98.  
  
-   Ladění ve smíšeném režimu (nativní nebo spravovaný).  
  
-   Ladění jazyka JavaScript.  
  
-   Ladění SQL.  
  
-   Souboru s výpisem ladění.  
  
-   Úpravy kódu po neošetřené výjimky, když **Unwind zásobníku volání na neošetřených výjimek** možnost není vybraná.  
  
-   Ladění aplikace pomocí **připojit k** namísto spuštění aplikace tak, že zvolíte **spustit** na **ladění** nabídky.  
  
-   Ladění optimalizovaného kódu.  
  
-   Ladění starší verzi kódu po novou verzi se nepodařilo sestavit z důvodu chyby sestavení.  
  
##  <a name="BKMK_Linking_limitations"></a>Omezení propojení  
  
###  <a name="BKMK_Linker_options_that_disable_Edit_and_Continue"></a>Možnosti linkeru, které zakázat upravit a pokračovat  
 Následující možnosti linkeru zakázat upravit a pokračovat:  
  
-   Nastavení **/OPT:REF**, **/OPT:ICF**, nebo **/INCREMENTAL:NO** zakáže upravit a pokračovat s následujícím upozorněním:  
  
     ODKAZ: upozornění LNK4075: ignoruje /EDITANDCONTINUE z důvodu/OPT  
  
     specifikace  
  
-   Nastavení **/pořadí**, **/RELEASE**, nebo **/FORCE** zakáže upravit a pokračovat se toto upozornění:  
  
     ODKAZ: upozornění LNK4075: / incremental je ignorována z důvodu/Option  
  
     specifikace  
  
-   Nastavení všechny možnosti, které brání vytvoření souboru databáze (.pdb) program zakáže upravit a pokračovat bez konkrétní upozornění.  
  
###  <a name="BKMK_Auto_relinking_limitations"></a>Automatické opakované propojování omezení  
 Ve výchozím nastavení upravit a pokračovat relinks vašeho programu na konci relace ladění k vytvoření aktuální spustitelný soubor.  
  
 Znovu vašeho programu nelze propojit upravit a pokračovat, pokud ladíte z umístění než na původní umístění sestavení. Zobrazí se zpráva, že budete muset znovu vytvořit ručně.  
  
 Upravit a pokračovat není znovu sestavit statických knihoven. Pokud provedete změny statické knihovny pomocí upravit a pokračovat, budete muset ručně znovu vytvořit aplikace knihovny a změnit vazbu pro jeho použití.  
  
 Funkce Upravit a pokračovat nevyvolává vlastní kroky sestavení. Pokud program používá vlastní kroky sestavení, je nutné provést ruční opětovné sestavení, aby se vyvolaly vlastní kroky sestavení. V tom případě je možné vypnout propojování po funkci Upravit a pokračovat, aby bylo zaručeno, že budete vyzváni, abyste provedli ruční znovu sestavení.  
  
 **Zakázat opakované propojování po upravit a pokračovat**  
  
1.  Na **ladění** nabídce zvolte **možnosti a nastavení**.  
  
2.  V **možnosti** dialogovém **ladění** uzel a vyberte možnost **upravit a pokračovat** uzlu.  
  
3.  Vymazat **znovu připojit změny kódu po ladění** zaškrtávací políčko.  
  
##  <a name="BKMK_Precompiled_Header_Limitations"></a>Omezení předkompilovaných hlaviček  
 Ve výchozím nastavení upravit a pokračovat předkompilovaných hlaviček zatížení a procesy na pozadí pro urychlení zpracování změn kódu. Načítání předkompilovaných hlaviček vyžaduje přidělení fyzické paměti, což může být problém, pokud jsou kompilování na počítači s omezenou paměti RAM. Můžete určit, pokud to může být problém pomocí Správce úloh systému Windows k určení množství dostupné fyzické paměti při ladění. Pokud je tato hodnota vyšší než velikost předkompilovaných hlaviček, pak by funkce Upravit a pokračovat neměla mít problém. Pokud velikost je menší než velikost předkompilovaných hlaviček, můžete zabránit upravit a pokračovat v načítání předkompilovaných hlaviček na pozadí.  
  
 **Chcete-li zakázat načítání na pozadí předkompilovaných hlaviček pro upravit a pokračovat**  
  
1.  Na **ladění** nabídce zvolte **možnosti a nastavení**.  
  
2.  V **možnosti** dialogovém **ladění** uzel a vyberte možnost **upravit a pokračovat** uzlu.  
  
3.  Vymazat **povolit předkompilace** zaškrtávací políčko.  
  
##  <a name="BKMK_IDL_Attribute_Limitations"></a>Omezení pro atribut IDL  
 Upravit a pokračovat neobnoví souborů definic (IDL) rozhraní. Proto změny IDL – atributy neodrazí se v průběhu ladění. Pokud chcete zobrazit výsledek změny IDL – atributy, musí Zastavte ladění a sestavte znovu vaší aplikace. Upravit a pokračovat negeneruje chybě nebo upozornění Pokud IDL – atributy se změnila. Další informace najdete v tématu [IDL – atributy](/cpp/windows/idl-attributes).  
  
## <a name="see-also"></a>Viz také  
 [Upravit a pokračovat (Visual C#)](../debugger/edit-and-continue-visual-cpp.md)