---
title: "Test oblasti 3: Kontrola odesílací zrušit rezervaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, checkout
- source control plug-ins, undo checkout
- source control [Visual Studio SDK], checking out
- source control [Visual Studio SDK], undo checkout
ms.assetid: ce00c5a5-d472-4f45-8776-d77a1fbe9d37
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8835f1f8c312b3aba72353625a1d97b514dc21b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="test-area-3-check-outundo-checkout"></a>Test oblasti 3: Rezervovat / vrátit zpět rezervaci
Tato oblast modulu plug-in testovací zdrojového kódu zahrnuje úpravy a navrácení položky z úložiště verzí prostřednictvím **rezervovat** a **vrátit zpět rezervaci** příkazy.  
  
 **Rezervovat**: značky položky v úložišti verze jako rezervována, upraví místní kopii pro čtení a zápis.  
  
 **Vrátit zpět rezervaci**: označí položky v úložišti verze jako změnami, vrátí místní kopie do stavu před rezervaci (v závislosti na možnosti).  
  
## <a name="command-menu-access"></a>Příkaz přístup do nabídky  
 Následující [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] cesty nabídky integrované vývojové prostředí se používají v testovací případy.  
  
##### <a name="check-out"></a>Mrkni se:  
  
-   **Soubor**, **ovládací prvek zdroje**, **rezervovat**.  
  
-   **Soubor**, **rezervovat**.  
  
-   Místní nabídky, **rezervovat**.  
  
-   Najdete v článku věnovaném vrácení zpět: **soubor**, **ovládací prvek zdroje**, **vrátit zpět rezervaci**.  
  
## <a name="common-expected-behavior"></a>Běžné očekávané chování  
  
-   Po rezervaci operaci jsou cílové soubory a složky označené jako rezervována v úložišti verze.  
  
-   Úložiště verzí atributy rezervaci správné uživateli.  
  
-   Data a času rezervaci správnost (podle nastavení uživatele).  
  
## <a name="test-cases"></a>Testovací případy  
 Níže jsou uvedeny konkrétní testovací případy oblasti testu najdete v článku věnovaném najdete v článku věnovaném nebo vrácení zpět.  
  
### <a name="case-3a-check-out"></a>Případ 3a: Podívejte se na  
 Tato část se zaměřuje na operaci vydání příkazu.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Zkontrolujte si výhradní (COE) klientského projektu|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Podívejte se na celý projekt výhradně (**soubor**, **rezervovat**).|Nastane, podívejte se na.|  
|Podívejte se na exkluzivní (COE) systému souborů nebo projektu místní služby IIS|1.  Nastavení připojení webového serveru do sdílené složky v souboru **nástroje**, **možnosti**, **projekty**, **nastavení webu**.<br />2.  Vytváření webového projektu.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Podívejte se na celý projekt výhradně (**soubor**, **správy zdrojového kódu**, **rezervovat**).|Nastane, podívejte se na.|  
|Podívejte se na položky řešení v řešení (nový způsob zpracování další soubory)|1.  Vytvoření prázdného řešení.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Podívejte se na řešení.<br />4.  Přidejte několik položek řešení.<br />5.  Všechny nově přidané položky se změnami.<br />6.  Vyberte více položek řešení.<br />7.  Podívejte se na vybrané položky (místní nabídky, **rezervovat**).|Vybrané soubory jsou rezervována.|  
|Zkontrolujte si místní verze (Pokud tuto funkci podporuje modul plug-in testovaného)|1.  Uživatel 1: Vytvoření projektu klienta.<br />2.  Uživatel 1: Přidání řešení do správy zdrojového kódu.<br />3.  Uživatel 2: Otevřete řešení od správy zdrojového kódu do jiného umístění.<br />4.  Uživatel 2: Podívejte se na soubor.<br />5.  Uživatel 2: Daný soubor upravte.<br />6.  Uživatel 2: Zkontrolujte v souboru.<br />7.  Uživatel 1: Podívejte se na místní verzi souboru (zkontrolujte **zkontrolujte si místní verze** rozšířené možnosti v **rezervovat** dialogové okno).|Místní verzi souboru je rezervována.<br /><br /> Úpravy uživatelem 2 nebyly použity u uživatele 1 souboru.|  
  
### <a name="case-3b-disconnected-check-out"></a>Případ 3b: odpojení podívejte se na  
 V odpojeném režimu umožňuje uživatelům určité úrovně trvalá zdroj ovládacího prvku podpory když nejsou připojené přímo k úložišti verzí. K tomu je potřeba místně ukládání do mezipaměti všechny relevantní informace o zařazené řešení a projekty.  
  
 Výhradní rezervaci operace může dojít pouze během připojení k úložišti zdroj ovládacího prvku. Sdílené rezervaci operations může dojít kdykoliv, zda připojení nebo odpojení. Proto při odpojení od úložiště verzí, jenom **zaškrtněte na sdílených** (COS) příkaz je povolen. Při odpojení, **vrátit zpět rezervaci** je zakázána, protože předchozí verzi nelze načíst nahradit změny provedené uživatelem.  
  
 Když se uživatel znovu připojí na verzi uložit, najdete v článku věnovaném stavy všech zařazené řešení a projekty jsou synchronizovány. To funguje potřebné aktualizace do úložiště pro rezervace, které uživatel provedl. Po synchronizaci došlo, je uživatel moci pokračovat v práci jako normální (připojený).  
  
#### <a name="expected-behavior"></a>Očekávané chování  
  
-   Nelze použít **zkontrolujte si výhradně** příkaz odpojené od úložiště verzí.  
  
-   Nelze použít **vrátit zpět rezervaci** příkaz odpojené od úložiště verzí.  
  
-   **Sdílená zkontrolujte** příkaz funguje.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Při odpojení, podívejte se na soubor a potom připojení pro synchronizaci|1.  Odpojit řízené projektu pomocí dialogového okna změnu zdrojového kódu (**soubor**, **správy zdrojového kódu**, **ivní Změna zdroje ovládání**l).<br />2.  Projděte si soubor.<br />3.  Klikněte na tlačítko rezervaci (při odpojení) v dialogovém okně upozornění.<br />4.  Upravte soubor.<br />5.  Připojte pomocí dialogového okna změnu zdrojového kódu.<br />6.  Získáte nejnovější verzi upravený soubor.|Běžné očekávané chování|  
  
### <a name="case-3c-query-editquery-save-qeqs"></a>Případ 3c: Upravit dotaz nebo dotaz uložit (QEQS)  
 Položky v rámci správy zdrojového kódu jsou sledovány pro úpravy, změny, a uloží usnadnit uživatelům snadno spravovat svoje soubory. Když upravíte řízené položku, která je "zkontrolovat v" QEQS zachycuje pokus o úpravu a požádá uživatele, pokud chce rezervovat soubor jej upravit. V závislosti na **nástroje**, **možnosti** nastavení, uživatel je buď nuceno zkontrolujte out souboru, aby bylo možné upravit nebo může být povoleno upravit jeho kopii v paměti a podívejte se na později. Pokud uživatele **nástroje**, **možnosti** není nastavení k zobrazení rezervaci dialogové okno a právě zkontrolujte ho a potom jako uživatel provede jeho úpravy, soubor automaticky rezervuje, kdykoli je to možné.  
  
#### <a name="expected-behavior"></a>Očekávané chování  
  
-   Po rezervaci operaci jsou cílové soubory a složky označené jako rezervována v úložišti verze.  
  
-   Úložiště verzí atributy rezervaci správné uživateli.  
  
-   Data a času rezervaci správnost (podle nastavení uživatele).  
  
-   Je místní kopie na cílový soubor nebo složku nelze zapisovat.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Upravit textový soubor, který se změnami|1.  Vytvořte nový projekt obsahující textového souboru.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu**, **umožňují upravit, pokud na disku jen pro čtení souborů** na nezaškrtnuté.<br />4.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu**, **výzva k rezervaci** v **při kontrole soubory jsou upravených** – pole se seznamem.<br />5.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu**, **výzva k rezervaci** v **v případě zaškrtnutíukládánísouborů** – pole se seznamem.<br />6.  V editoru otevřete textový soubor se pokusit zadat nový text do souboru. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />7.  Klikněte na tlačítko **zrušit** v **rezervovat pro úpravy** dialogové okno. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />8.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu**, **umožňují upravit, pokud na disku jen pro čtení souborů** na zaškrtnuté.<br />9. V editoru otevřete soubor projektu se pokusit zadat nový text v souboru. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />10. Klikněte na tlačítko **upravit** v **rezervovat pro úpravy** dialogové okno. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />11. Upravit textový soubor a pokusí se ji uložit.|`Result of step 6:`<br /><br /> Rezervujte pro zobrazí se dialogové okno Upravit.<br /><br /> `Result of step 7:`<br /><br /> Soubor se nezmění.<br /><br /> `Result of step 9:`<br /><br /> Rezervujte pro zobrazí se dialogové okno Upravit.<br /><br /> `Result of step 10:`<br /><br /> Můžete upravit soubor projektu v paměti.<br /><br /> `Result of step 11:`<br /><br /> Na Uložit rezervaci na Uložit dialogové okno se zobrazí.|  
|Upravit soubor řešení, která je vrácena se změnami|Opakujte kroky, jak je popsáno v předchozí testovací ale místo úpravy textového souboru, upravte řešení změnou vlastností řešení.|Stejné jako v předchozím testu|  
|Upravit soubor projektu, který se změnami|Opakujte kroky, jak je popsáno v předchozí testování, ale místo úpravy textového souboru, upravte projektu změnou vlastností projektu.|Stejné jako v předchozím testu.|  
  
### <a name="case-3d-silent-check-out"></a>Případ 3d: Tichou podívejte se na  
 Tento dílčí oblasti zahrnuje rezervaci scénáře kde **rezervovat** na uživatele se dialogové okno **nástroje**, **možnosti**, **nastavení správy zdrojového kódu** .  
  
#### <a name="expected-behavior"></a>Očekávané chování  
  
-   Po rezervaci operaci jsou cílové soubory a složky označené jako rezervována v úložišti verze.  
  
-   Úložiště verzí atributy rezervaci správné uživateli.  
  
-   Data a času rezervaci je správná (podle nastavení uživatele).  
  
-   Je místní kopie na cílový soubor nebo složku nelze zapisovat.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Tichou najdete v článku věnovaném souboru|1.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu** k **souborů najdete v článku věnovaném automaticky na Úpravy**.<br />2.  Vytvoření nového projektu pomocí souboru.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Podívejte se na soubor.|Soubor je rezervovaný bezobslužně (bez uživatelského rozhraní).|  
|Tichou rezervovat pro projekt|1.  Nastavit **nástroje**, **možnosti**, **správy zdrojového kódu** k **souborů najdete v článku věnovaném automaticky na Úpravy**.<br />2.  Vytvořte nový projekt.<br />3.  Přidáte řešení do správy zdrojového kódu.<br />4.  Podívejte se na projektu.|Soubor je rezervovaný bezobslužně (bez uživatelského rozhraní).|  
  
### <a name="case-3e-undo-check-out"></a>Případ 3e: vrátit zpět rezervaci  
 **Vrátit zpět rezervaci** se používá k zrušit souboru rezervována stav a vyhnout se kontroluje změny provedené v souboru.  
  
#### <a name="expected-behavior"></a>Očekávané chování  
  
-   Výchozí hodnota je založena na uživatele **podívejte se na místní verze** nastavení. Pokud uživatel zvolil podívejte se na místní verze, potom na výchozí hodnoty pro vrácení zpět najdete v článku věnovaném je vždy vrátit k verzi rezervována.  
  
-   Po přijetí vrácení zpět, ikony v **Průzkumníku řešení** jsou aktualizované vliv soubory a položky se odebere z **čeká na vrácení se změnami** okno.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Vrátit zpět rezervaci jeden soubor, který je rezervována výhradně|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Projděte si soubor výhradně.<br />4.  Upravte soubor.<br />5.  Vrátit zpět rezervaci (**soubor**, **ovládací prvek zdroje**, **vrátit zpět rezervaci**).|Běžné očekávané chování.|  
|Vrátit zpět rezervaci jeden soubor, který je rezervována sdílené|1.  Vytvoření projektu klienta.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Projděte si soubor sdílený.<br />4.  Upravte soubor.<br />5.  Vrátit zpět rezervaci (**soubor**, **ovládací prvek zdroje**, **vrátit zpět rezervaci**).|Běžné očekávané chování.|  
|Vrátit zpět rezervaci projektu po přidání souborů do projektu|1.  Vytvoření nového projektu a přidat jej do správy zdrojového kódu.<br />2.  Podívejte se na projektu.<br />3.  Přidá soubor do projektu.<br />4.  Vrátit zpět, najdete v článku věnovaném projektu.|Přidaný soubor bude odstraněn z projektu v Průzkumníku řešení.<br /><br /> Projekt je již rezervován.|  
|Vrátit zpět rezervaci projektu po odstranění soubory z projektu|1.  Vytvoření nového projektu a přidat jej do správy zdrojového kódu.<br />2.  Podívejte se na projektu.<br />3.  Odstranění souboru z projektu.<br />4.  Vrátit zpět, najdete v článku věnovaném projektu.|Odstraněnému souboru se zobrazí pod na projekt v Průzkumníku řešení.<br /><br /> Projekt je již rezervován.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)