---
title: "Použití souborů výpisu paměti | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 03/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.crashdump
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- dumps, about dumps
- crash dumps
- dump files
- dumps
ms.assetid: b71be6dc-57e0-4730-99d2-b540a0863e49
caps.latest.revision: "53"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 179d66b80676cf47bb12e82fcd8e4ac00503a492
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="use-dump-files-with-visual-studio"></a>Použití souborů výpisu paměti pomocí sady Visual Studio
Soubory s nebo bez haldách; výpisů Vytvořte soubor výpisu; Otevřete soubor s výpisem; Najít binární soubory, na pdb a zdrojového souboru pro souboru výpisu.
  
##  <a name="BKMK_What_is_a_dump_file_"></a>Co je soubor výpisu?  
 A *souboru s výpisem* je snímek aplikace v bodě v čase výpisu nebyla provedena. Ukazuje, jaký proces probíhal a které moduly byly načteny. Pokud byl výpis paměti uložen s informacemi o haldě, soubor s výpisem paměti obsahuje snímek toho, co bylo v paměti aplikace v daném okamžiku. Otevření souboru s výpisem paměti pomocí haldy v sadě Visual Studio odpovídá zastavení na zarážce v ladicí relaci. Ačkoli nelze pokračovat v provádění, můžete zkoumat zásobníky, vlákna a proměnné hodnoty aplikace v době, kdy došlo k výpisu paměti.  
  
 Výpisy se primárně používají pro ladění problémů, ke kterým došlo na počítačích, které vývojář nemá přístup k. Můžete například souboru s výpisem z počítače zákazníka při nelze reprodukovat havárií zákazníka nebo zablokuje na váš počítač. Výpisy paměti jsou vytvářeny také testery, kteří v nich ukládají data o zhroucení nebo zablokování, aby bylo možné testovací počítač použít pro další testování. Ladicí program Visual Studio může uložit soubory s výpisem paměti pro spravovaný nebo nativní kód. Ladicí program můžete načíst výpisu soubory, které byly vytvořeny pomocí sady Visual Studio nebo jinými programy, které umístění souborů *minimální výpis* formátu.  
  
##  <a name="BKMK_Dump_files__with_or_without_heaps"></a>Výpis souborů, s nebo bez hald  
 Můžete vytvořit soubory s výpisem paměti s informacemi o haldě nebo bez nich.  
  
-   **Soubory s haldách výpisů** obsahovat snímek paměti aplikace. Zahrnuje hodnoty proměnných v době, kdy byl vytvořen výpis paměti. Pokud načtete soubor s výpisem paměti, který byl uložen s haldou, sada Visual Studio může načíst symboly i v případě, že binární soubor aplikace není nalezen. Visual Studio také ukládá binární verze načtených nativních modulů v souboru s výpisem paměti, díky čemu může být ladění mnohem snazší.  
  
-   **Soubory bez haldách výpisů** jsou mnohem menší než výpisů paměti haldy informace. Ladicí program má však načíst binární soubory aplikace a nalézt tak informace o symbolu. Binární soubory musí být přesná shoda binárních souborů, které byly použity při vytvoření výpisu paměti. Pouze hodnoty proměnných zásobníku jsou ukládány do souborů výpisu paměti bez dat haldy.  
  
##  <a name="BKMK_Requirements_and_limitations"></a>Požadavky a omezení  
  
-   Ladění souborů s výpisem paměti pro optimalizaci kódu může být matoucí. Například vkládání funkcí kompilátoru může mít za následek neočekávané volání zásobníků a další optimalizace může upravit délku platnosti proměnných.  
  
-   Soubory s výpisem paměti u 64bitových počítačů je nutné ladit v instanci aplikace Visual Studio, která běží na 64bitovém počítači.  
  
-   Ve verzích sady Visual Studio před verzí 2013 výpisy paměti 32bitových aplikací běžících v 64bitových počítačích, které byly shromážděny pomocí některých nástrojů (například Správce úloh a WinDbg v 64bitové verzi) nelze otevřít v sadě Visual Studio. Toto omezení bylo ve verzi 2013 odebráno.  
  
-   Visual Studio můžete ladit soubory s výpisem paměti nativních aplikaci ze zařízení ARM. Visual Studio může také ladit soubory s výpisem paměti aplikací spravovaných aplikace ze zařízení ARM, avšak pouze v nativním ladicím programu.  
  
-   Chcete-li ladit [režimu jádra](http://msdn.microsoft.com/library/windows/hardware/ff551880.aspx) soubory výpisů, stáhněte si ladicí nástroje pro systém Windows, který je součástí [ovladač Kit WDK (Windows)](/windows/hardware/windows-driver-kit). 
  
-   Visual Studio nemůže ladění souborů výpisu paměti, které jsou uloženy ve starším formátu výpisu známé jako [úplné uživatelského režimu výpisu](http://msdn.microsoft.com/library/windows/hardware/ff545506.aspx). Pamatujte, že výpis paměti s úplným uživatelským režimem není stejný jako výpis s daty haldy.  
  
-   Ladění [SOS.dll (rozšíření ladění SOS)](/dotnet/framework/tools/sos-dll-sos-debugging-extension) v sadě Visual Studio, je nutné nainstalovat nástroje ladění pro Windows, která je součástí [ovladač Kit WDK (Windows)](/windows/hardware/windows-driver-kit) 
  
##  <a name="BKMK_Create_a_dump_file"></a>Vytvoření souboru výpisu  
 Vytvoření souboru s výpisem paměti pomocí aplikace Visual Studio:  
  
-   Při ladění procesu v aplikaci Visual Studio, můžete uložit soubor s výpisem paměti, když se ladicí program zastaví na výjimce nebo v bodu přerušení. Zvolte **ladění**, pak **uložit výpisu jako**, pak **ladění**. V **uložit Dump jako** dialogu **uložit jako typ** seznamu můžete vybrat **minimální výpis** nebo **minimální výpis s haldy** (výchozí).  
  
-   S [ladění JIT](../debugger/just-in-time-debugging-in-visual-studio.md) povolená, můžete připojit ladicí program k zhroucené procesu, který je spuštěn mimo ladicí program a potom uložte soubor výpisu. V tématu [připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
  
 Můžete také vytvořit soubory s výpisem paměti pomocí libovolného programu, který podporuje formát minimálního výpisu Windows. Například **Procdump** nástroj příkazového řádku z [webu Windows Sysinternals](http://technet.microsoft.com/sysinternals/default) můžete vytvořit souborů výpisu paměti procesu havárií na základě aktivační události nebo na vyžádání. V tématu [požadavky a omezení](../debugger/using-dump-files.md#BKMK_Requirements_and_limitations) v tomto tématu pro další informace o vytvoření výpisu souborů pomocí jiných nástrojů. 
  
##  <a name="BKMK_Open_a_dump_file"></a>Otevřete soubor výpisu  
  
1.  V sadě Visual Studio, vyberte **soubor**, **otevřete**, **soubor**.  
  
2.  V **otevření souboru** dialogové okno pole, vyhledejte a vyberte soubor výpisu. Obvykle má příponu .dmp. Zvolte **OK**.  
  
3.  **Dump shrnutí souboru** se zobrazí v okně. V tomto okně můžete zobrazit souhrnné informace o ladění pro soubor s výpisem paměti, nastavit cestu symbolů, spustit ladění a souhrnné informace zkopírovat do schránky.  
  
     ![Souhrnná stránka minimální výpis](../debugger/media/dbg_dump_summarypage.png "DBG_DUMP_SummaryPage")  
  
4.  Pokud chcete začít, ladění, přejděte na **akce** části a vyberte buď **ladění se spravovat pouze**, **ladění se pouze nativní** nebo **ladění se Mixed**.  
  
##  <a name="BKMK_Find_binaries__symbol___pdb__files__and_source_files"></a>Najít binární soubory, soubory symbolu (.pdb) a zdrojové soubory  
 Chcete-li používat úplné funkce aplikace Visual Studio pro ladění souboru s výpisem paměti, potřebujete přístup k:  
  
-   Soubor .exe, pro který byl pořízen výpis paměti přijatých a další binárních souborů (knihovny DLL, atd.), které byly použity v procesu s výpisem paměti.  
  
     Jestliže ladíte výpis paměti s daty haldy, sada Visual Studio se může vypořádat s chybějícími binárními soubory pro některé moduly, ale musí mít binární soubory pro dostatek modulů, aby mohla vygenerovat platné zásobníky volání. Visual Studio obsahuje nativní moduly v souboru s výpisem paměti s haldou.  
  
-   Soubory symbolů (PDB) .exe a další binární soubory.  
  
-   Zdrojové soubory pro moduly, které vás zajímají.  
  
     Spustitelné soubory a soubory PDB musí odpovídat přesně verzi a sestavení souborů použitých při tvorbě výpisu paměti.  
  
     Můžete ladit pomocí zpětný překlad modulů, pokud nemůžete najít zdrojové soubory  
  
 **Výchozí cesty hledání pro spustitelné soubory**  
  
 Visual Studio automaticky vyhledá těchto umístění pro spustitelné soubory, které nejsou zahrnuté v souboru výpisu:  
  
1.  Adresář obsahující soubor s výpisem paměti.  
  
2.  Cesta modulu, který je zadaný v souboru s výpisem paměti. Toto je cesta modulu v počítači, kde byl výpis paměti shromážděn.  
  
3.  Symbol cesty zadané v **ladění**, **možnosti**, **symboly** stránky sady Visual Studio **nástroje**, **možnosti**  dialogové okno. Můžete přidat více míst pro vyhledávání na této stránce.  
  
 **Pomocí binární ne > Symbol > zdrojové stránky**  
  
 Pokud Visual Studio nemůže najít soubory potřebné pro ladění modulu ve výpisu, zobrazí odpovídající stránky (**binární nalezen žádný**, **najít žádné symboly**, nebo **nalezen žádný zdroj**). Tyto stránky obsahují podrobné informace o příčině problému a poskytují odkazy na akce, které vám mohou pomoci identifikovat správné umístění souborů. V tématu [zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [IntelliTrace](../debugger/intellitrace.md)