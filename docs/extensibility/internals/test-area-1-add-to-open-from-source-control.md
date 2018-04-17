---
title: 'Oblasti test 1: Přidání k otevření od správy zdrojového kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], adding and opening solutions
- source control plug-ins, adding and opening solutions
ms.assetid: 5b3b5b08-5e9b-41be-ac72-c63957faed22
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e95ef13a3d8f7a61c53c9938564479adf362a2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="test-area-1-add-toopen-from-source-control"></a>Oblasti test 1: Přidání do nebo otevřete od správy zdrojového kódu
Tento modul plug-in správy zdroje otestovat zahrnuje oblasti umístění řešení nebo projekty ve správě zdrojového kódu a jejich načítání od správy zdrojového kódu.  
  
## <a name="command-menu-access"></a>Příkaz přístup do nabídky  
 Následující [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] cesty nabídky integrované vývojové prostředí se používají v testovací případy:  
  
-   Pro [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], otevřete od správy zdrojového kódu: **soubor**, **otevřete**, **projektu**/**řešení**; vyhledejte v [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] umístění.  
  
-   Pro jiné zdroje řízení moduly plug-in, otevřete od správy zdrojového kódu: **soubor**, **správy zdrojového kódu**, **otevřete od správy zdrojového kódu**.  
  
-   Přidat do správy zdrojového kódu: **soubor**, **správy zdrojového kódu**, **přidat řešení zdrojový soubor ovládacího prvku**, **správy zdrojového kódu**, **přidat Vybrané projekty do správy zdrojového kódu**.  
  
-   Místní nabídky (projekt nebo řešení) **přidat řešení do správy zdrojového kódu**.  
  
-   Přidat od správy zdrojového kódu: **soubor**, **správy zdrojového kódu**, **přidat projekt od správy zdrojového kódu**.  
  
-   Pro [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], přidejte ze zdroje ovládací prvek je k dispozici také z **soubor**, **přidat**, **existující projekt**; vyhledejte v [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] umístění.  
  
    > [!NOTE]
    >  Cesta místního souboru nebo místní služby IIS (web server) lze v tomto testu.  
  
## <a name="expected-behavior"></a>Očekávané chování  
  
-   Pro každý typ podporované projektu by mohli "Přidat" a "Otevřít z" Správa zdrojového kódu uživatele.  
  
-   Po přidání projektu do zdrojového kódu, odpovídající \< *ProjectName*> .SCC soubor (soubor projektu pomocný parametr) je vytvořen. Obsahuje vyloučení souboru seznamu a informace o připojení. Neodstraňujte tento soubor, protože obsahuje informace o projektu.  
  
-   Když se řešení přidá do zdrojového kódu, odpovídající \< *název řešení SolutionName*> se vytvoří soubor .vssscc (triple S). Textový soubor obsahuje informace o připojení a soubor seznamu vyloučení, podobně jako pomocný parametr souboru projektu. Tento soubor je dočasný a pouze v databázi pro správu zdrojů existuje.  
  
-   Po otevření řešení od správy zdrojového kódu \< *název řešení SolutionName*> soubor .vsscc (dvojité S), který existuje pouze v databázi zdrojové ovládací prvek, je vytvořena místně v dočasném souboru. Tento soubor obsahuje cestu k souboru řešení ze složky připojení řešení. Tento soubor je dočasný a místní kopie se odstraní po dokončení operace "Otevřete ze zdrojového kódu".  
  
-   Po přidání projektu k řízení zdrojů vám může provádět všechny akce zdroj ovládacího prvku na něm (podívejte se na Get a tak dále).  
  
## <a name="test-cases"></a>Testovací případy  
 Toto jsou konkrétní testovací případy pro přidat do nebo z oblasti testovací zdrojového kódu otevřete.  
  
### <a name="case-1a-add-solution-to-source-control"></a>Případ 1a: přidání řešení do správy zdrojového kódu  
 Tento testovací případ se zaměřuje na přidání řešení do správy zdrojového kódu.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Přidat řešení obsahující klientského projektu do správy zdrojového kódu|1.  Vytvoření projektu klienta.<br />2.  Přidat řešení do správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat řešení správy zdrojového kódu**).|Řešení/projekt byl přidán do správy zdrojového kódu.|  
|Přidat řešení obsahující systému souborů nebo místní služby IIS webového projektu do správy zdrojového kódu|1.  Vytvoření projektu místní služby IIS nebo systému souborů (použijte tlačítko Procházet přejděte do umístění projektu; cesta Určuje, jaký typ webového projektu se vytvoří).<br />2.  Přidat řešení do správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat řešení správy zdrojového kódu**).|Řešení/projekt byl přidán do správy zdrojového kódu.|  
|Přidat řešení obsahující vzdálené lokality webového projektu do správy zdrojového kódu|1.  Vytvoření projektu vzdáleném webovém serveru.<br />2.  Přidat řešení do správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat řešení správy zdrojového kódu**).<br />3.  Klikněte na tlačítko **OK** v dialogovém okně upozornění FrontPage přístup.|Řešení bylo přidáno do správy zdrojového kódu.<br /><br /> Vzdálený projekt není ve správě zdrojového kódu. (Projekty vzdálené lokality je třeba kontrolovat ze své vlastní server IIS.)|  
|Přidat řešení jedné projektu pomocí ovládacího prvku zdroj **přidat vybrané projekty do správy zdrojového kódu**.|1.  Vytvořte jeden projektu řešení.<br />2.  Přidat jenom řešení do správy zdrojového kódu jako výběr (**soubor**, **správy zdrojového kódu**, **přidat vybrané projekty do správy zdrojového kódu**). Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Přidat projekt do správy zdrojového kódu jako výběr (**soubor**, **správy zdrojového kódu**, **přidat vybrané projekty do správy zdrojového kódu**).<br />4.  Klikněte na tlačítko **Ano** přidat projekt do stejného umístění.<br />5.  Klikněte na tlačítko **rezervovat** v **zkontrolujte si pro úpravy** dialogové okno.|`Result from Step 2:`<br /><br /> Projekt a všechny soubory v projektu existuje vrácená se indikátor řízení zdroje a zobrazí popisek "není v části Správa zdrojového kódu".<br /><br /> `Result from Step 5:`<br /><br /> Soubor projektu a řešení jsou ve stejné složce ve správě zdrojového kódu.|  
|Zrušit přidání řešení do správy zdrojového kódu|1.  Vytvořte jeden projektu řešení.<br />2.  Pokus o přidání projektu a řešení k řízení zdrojů. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zrušte, jakmile se v systému správy zdrojů.|`Result from Step 2:`<br /><br /> Pouze jednou se zobrazí dialogové okno sady zdrojové umístění projektu ovládacího prvku.<br /><br /> `Result from Step 3:`<br /><br /> Projektu přidejte zrušené, projekt nebo řešení není ve správě zdrojového kódu a všechny přidejte do nabídek na ovládací prvek zdroje, které jsou stále k dispozici.|  
  
### <a name="case-1b-open-solution-from-source-control"></a>Case 1b. Otevřete řešení od správy zdrojového kódu  
 Tento testovací případ se zaměřuje na otevírání řešení od správy zdrojového kódu.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Otevřete řešení obsahující projektu klienta od správy zdrojového kódu|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení od správy zdrojového kódu do nového umístění.|Řešení nebo projektu otevřít od správy zdrojového kódu.|  
|Otevřete řešení obsahující místní nebo IIS webového projektu ze správy zdrojového kódu|1.  Vytvořte místní nebo projektu služby IIS.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení od správy zdrojového kódu do nového umístění.|Řešení nebo projektu otevřít od správy zdrojového kódu.|  
|Otevřete řešení obsahující vzdálené lokality webového projektu ze správy zdrojového kódu|1.  Vytvoření projektu vzdáleném webovém serveru.<br />2.  Přidáte řešení do správy zdrojového kódu. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zavřete řešení.<br />4.  Otevřete řešení od správy zdrojového kódu do nového umístění.|`Result from Step 2:`<br /><br /> Vzdálený webový server není ve správě zdrojového kódu.<br /><br /> `Result from Step 4:`<br /><br /> Otevřít řešení od správy zdrojového kódu.<br /><br /> Načtení projektu vzdálené lokality, ale není v části Správa zdrojového kódu.|  
  
### <a name="case-1c-add-solution-from-source-control"></a>Případ 1c: Přidat řešení od správy zdrojového kódu  
 Tento testovací případ se zaměřuje na přidání řešení od správy zdrojového kódu.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Přidat do prázdné řešení – jeden projekt řešení|1.  Vytvořte jeden projektu řešení.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Vytvořte druhý prázdný řešení.<br />5.  Přidat dříve řízené řešení od správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat projekt od správy zdrojového kódu**).|Přidání projektu se zobrazí v **Průzkumníku řešení** a vrátí se změnami.|  
|Přidat do řešení s projektem jeden – jeden projektu|1.  Vytvoření řešení s projektem jeden.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Zavřete řešení.<br />4.  Vytvořte druhý prázdný řešení.<br />5.  Přidat dříve řízené řešení od správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat projekt od správy zdrojového kódu**).|Přidání projektu se zobrazí v **Průzkumníku řešení** a vrátí se změnami.|  
|Přidat do řešení – řešení ve výběru přidány do správy zdrojového kódu|1.  Vytvoření řešení s projektem.<br />2.  Přidejte jenom řešení do správy zdrojového kódu jako výběr. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />3.  Zavřete řešení.<br />4.  Vytvořte nové řešení.<br />5.  Přidat dříve řízené řešení od správy zdrojového kódu (**soubor**, **správy zdrojového kódu**, **přidat projekt od správy zdrojového kódu**).|`Result from Step 2:`<br /><br /> Projekt není ve správě zdrojového kódu.<br /><br /> `Result from Step 5:`<br /><br /> Pokud první řešení měl položky řešení, není možné je přidat od správy zdrojového kódu, se nezobrazí.<br /><br /> Projekt z první řešení se objeví jako nedostupné.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)