---
title: 'Testovací oblasti 5: Změnit Správa zdrojového kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], changing
- source control plug-ins, changing source control
ms.assetid: fdf09e00-108c-4d51-bbd5-72452d52a490
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e7fd014bf520ee2f0515e284f2fb5430961cd407
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134341"
---
# <a name="test-area-5-change-source-control"></a>Test oblasti 5: Změna zdrojového kódu
Tato oblast modulu plug-in testovací zdrojového kódu zahrnuje změnu zdrojového kódu pomocí **změnu zdrojového kódu** příkaz.  
  
 **Správa zdrojového kódu změňte** příkaz nabízí čtyři základní funkce pro uživatele:  
  
-   **Vazby:**  
  
     Umožňuje uživateli k navázání nebo obnovení zdroj řízení propojení mezi řešení nebo projektu a úložiště verzí.  
  
-   **Zrušit vazbu:**  
  
     Odebere projekt nebo řešení od správy zdrojového kódu na základě jednotlivých připojení.  
  
-   **Připojit/odpojte:**  
  
 Přepíná stav řízené řešení, která je popsaná v oblasti 3 připojené nebo offline. Další informace najdete v tématu [testovací oblasti 3: Rezervovat / vrátit zpět rezervaci](../../extensibility/internals/test-area-3-check-out-undo-checkout.md).  
  
## <a name="command-menu-access"></a>Příkaz přístup do nabídky  
 Následující [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí nabídky Cesta se používá v testovací případy.  
  
 Změnu zdrojového kódu:**soubor**, **ovládací prvek zdroje**, **změnit zdrojového kódu**.  
  
## <a name="test-cases"></a>Testovací případy  
 Toto jsou pro konkrétní testovací případy **změnu zdrojového kódu** příkaz testovací oblasti.  
  
### <a name="case-5a-bind"></a>Případ 5a: vytvoření vazby  
 Vazby umožňuje uživateli přidat informace o řízení zdrojového kódu do vybraných projektů a řešení. Obvykle bude uživatel vyzván k identifikaci projektu ve správě zdrojového kódu, ke kterému jde přidat. Uživatele nelze vytvořit nový projekt ve správě zdrojového kódu v rámci této operace (kontrast s přidat do správy zdrojového kódu).  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Vytvořit vazbu na prázdný umístění|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Otevřete **změnu zdrojového kódu** dialogové okno (**soubor**, **správy zdrojového kódu**, **změnu zdrojového kódu**).<br />4.  Klikněte na tlačítko **zrušit vazbu**.<br />5.  Dialogové okno upozornění přijměte, pokud se zobrazí.<br />6.  Vyberte všechny položky.<br />7.  Klikněte na tlačítko **vazby**.<br />8.  Přejděte do prázdné umístění v úložišti zdroj ovládacího prvku.<br />9. Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />10. Klikněte na tlačítko **pokračovat s těmito vazby** v potvrzovacím dialogovém okně.<br />11. Klikněte na tlačítko **OK** v dialogovém okně upozornění, pokud se zobrazí.<br />12. Zkontrolujte v části všechno. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />13. Otevřete řešení od správy zdrojového kódu do nového umístění.|`Result from Step 12:`<br /><br /> Řešení a projektů jsou vázaná na a zapisovat do nového cíle v úložišti verze.<br /><br /> Soubory řešení a projektu se změnami.<br /><br /> Verze úložiště projektu hierarchie odpovídá hierarchii složek projektu na disku.<br /><br /> `Result from Step 13:`<br /><br /> Všechny položky projektu, se stáhnou.|  
|Vytvořit vazbu k umístění, které se synchronizuje s klientem|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Vytvořit duplicitní řešení a projektu v úložišti verze (sdílené složky a větev, pokud se používá [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />4.  Otevřete **změnu zdrojového kódu** dialogové okno (**soubor**, **správy zdrojového kódu**, **změnu zdrojového kódu**).<br />5.  Odpojení všechny.<br />6.  Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />7.  Znovu otevřete **změnu zdrojového kódu** dialogové okno.<br />8.  Vybrat vše.<br />9. Klikněte na tlačítko **vazby**.<br />10. Přejděte do umístění větvenou řešení a projektu (z kroku 3)<br />11. Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />12. Získejte nejnovější rekurzivně pro všechny položky.|Po zjištění je stejná jako předtím get souboru obsahu.|  
|Vytvořit vazbu k umístění, které je mimo rozsah synchronizace s klientem|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Vytvořit duplicitní řešení a projektu v úložišti verze (sdílené složky a větev, pokud se používá [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />4.  Upravte soubory v projektu větvenou v úložišti verze.<br />5.  Otevřete **změnu zdrojového kódu** dialogové okno (**soubor**, **správy zdrojového kódu**, **změnu zdrojového kódu**).<br />6.  Odpojení všechny.<br />7.  Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />8.  Znovu otevřete **změnu zdrojového kódu** dialogové okno.<br />9. Vybrat vše.<br />10. Klikněte na tlačítko **vazby**.<br />11. Přejděte do umístění pro řešení a projektu součástí podmínky.<br />12. Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />13. Dialogové okno upozornění přijměte, pokud se zobrazí.<br />14. Získejte nejnovější rekurzivní pro všechny položky.|Soubory, které byly změněny v kroku 4 jsou také upravit místně.|  
|Vytvoření vazby řešení, které se nikdy ve správě zdrojového kódu|1.  Vytvořte prázdnou složku ve správě zdrojového kódu.<br />2.  Vytvoření projektu klienta.<br />3.  Otevřete **změnu zdrojového kódu** dialogové okno (**soubor**, **správy zdrojového kódu**, **změnu zdrojového kódu**).<br />4.  Vytvoření vazby řešení s prázdnou umístění ve správě zdrojového kódu.<br />5.  Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />6.  Klikněte na tlačítko **pokračovat s těmito vazby** v potvrzovacím dialogovém okně.<br />7.  Klikněte na tlačítko **OK** v dialogovém okně upozornění, pokud se zobrazí.|Řešení se přidá do správy zdrojového kódu.<br /><br /> Řešení a projektů jsou rezervována.|  
|Zrušit vazby|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Otevřete dialogové okno Změnit zdrojového kódu.<br />4.  Odpojení všechny.<br />5.  Klikněte na tlačítko **OK** tlačítko dialogové okno zavřete. Pokud tento krok úspěšný, pokračujte dalším krokem.<br />6.  Otevřete **změnu zdrojového kódu** dialogové okno.<br />7.  Vytvoření vazby s nesouvisejícími umístění.<br />8.  Klikněte na tlačítko **zrušit**.|`Result from Step 5:`<br /><br /> Řešení je již ve správě zdrojového kódu<br /><br /> `Result from Step 8:`<br /><br /> Řešení je stále není v části Správa zdrojů.|  
  
### <a name="case-5b-unbind"></a>Případ 5b: odpojení  
 Odpojení odebere informace o řízení kód zdroje z projektů a jejich řešení. Ovlivněné projekty a řešení jsou založené na kombinaci výběr uživatele a jak byly přidány do správy zdrojového kódu.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Odpojení řešení obsahující jeden systému souborů nebo projektu místní služby IIS a jednoho klientského projektu|1.  Umožňuje vytvořte systém souborů nebo projektu místní služby IIS.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přidáte nový projekt klienta k řešení.<br />4.  Přijměte zkontrolujte z řešení, pokud se zobrazí výzva.<br />5.  Otevřete **změnu zdrojového kódu** dialogové okno.<br />6.  Klikněte na tlačítko **zrušit vazbu**.<br />7.  Klikněte na tlačítko **OK** zavřete dialogové okno.<br />8.  Pokuste se podívejte se na řešení, projektu, řešení položky, položky projektu.|Řešení a projekty nejsou ve správě zdrojového kódu.<br /><br /> Příkazy nabídky Zdroj ovládacího prvku se nezobrazí.|  
|Zrušit odpojení|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Otevřete **změnu zdrojového kódu** dialogové okno.<br />4.  Klikněte na tlačítko **odpojení všechny**.<br />5.  Klikněte na tlačítko **zrušit**.|Řešení je ve správě zdrojového kódu.|  
  
### <a name="case-5c-rebind"></a>Případ 5c: Rebind  
 Obnovení vazby je jednoduše kombinací vyjmout z pořadače a vazby – proces obnovení vazeb projekt nebo řešení, který byl dříve v části Správa zdrojového kódu a nevázaný.  
  
|Akce|Kroky testů|Očekávané výsledky ověření|  
|------------|----------------|--------------------------------|  
|Rebind – řešení a projekty bez zavření **změnu zdrojového kódu** dialogové okno|1.  Vytvořte projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Otevřete **změnu zdrojového kódu** dialogové okno.<br />4.  Klikněte na tlačítko **zrušit vazbu**.<br />5.  Vyberte všechny řádky.<br />6.  Klikněte na tlačítko **vazby**.<br />7.  Klikněte na tlačítko **OK** zavřete **změnu zdrojového kódu** dialogové okno.<br />8.  Pokud se zobrazí výzva, přijměte checkout.|Řešení a projektu jsou ve správě zdrojového kódu.|  
|Rebind projektu pouze bez uzavírací **změnu zdrojového kódu** dialogové okno|1.  Vytvořte projekt.<br />2.  Přidat pouze projekt pomocí ovládacího prvku zdroje (souboru -> Zdroj ovládacího prvku -> Přidat vybrané projekty k řízení zdrojů.<br />3.  Otevřete dialogové okno Změnit zdrojového kódu.<br />4.  Odpojení pouze projekt.<br />5.  Vytvořit vazbu jenom projektu.|Řešení zůstane neřízené.<br /><br /> Projekt zůstane řízené.|  
|Rebind řešení jenom bez uzavírací **změnu zdrojového kódu** dialogové okno|1.  Vytvořte projekt.<br />2.  Přidat jenom řešení pomocí ovládacího prvku zdroje (**soubor**, **správy zdrojového kódu**, **přidat vybrané projekty do správy zdrojového kódu**.<br />3.  Otevřete **změnu zdrojového kódu** dialogové okno.<br />4.  Zrušit vazbu jenom řešení (nezavírejte **změnu zdrojového kódu** dialogové okno.)<br />5.  Vytvořit vazbu jenom řešení.<br />6.  Klikněte na tlačítko **OK** zavřete dialogové okno.<br />7.  Podívejte se na řešení a položky řešení (pokud existuje)|Řešení zůstane řízené.<br /><br /> Projekt zůstane neřízené.|  
|Rebind řešení nebo projektu pouze ve stejném adresáři|1.  Vytvořte projekt.<br />2.  Přidat pouze projekt pomocí ovládacího prvku zdroje (**soubor**, **správy zdrojového kódu**, **přidat vybrané projekty do správy zdrojového kódu**.<br />3.  Zavřete řešení.<br />4.  Vytvořte nové řešení s alespoň dva projekty.<br />5.  Přidáte řešení do správy zdrojového kódu.<br />6.  Přidáte projekt vytvořili v kroku 1 od správy zdrojového kódu.<br />7.  Pokud se zobrazí výzva, přijměte checkout řešení.<br />8.  Zkontrolujte v celé řešení.<br />9. Otevřete **změnu zdrojového kódu** dialogové okno.<br />10. Vyberte projektu přidané (z kroku 6) a klikněte na **vyjmout z pořadače**.<br />11. Klikněte na tlačítko **OK** zavřete dialogové okno.<br />12. Rezervaci přijměte, pokud se zobrazí výzva.<br />13. Znovu otevřete **změnu zdrojového kódu** dialogové okno.<br />14. Vyberte projektu přidané (z kroku 6) a klikněte na **vazby**.<br />15. Vyberte na původní umístění.|Řešení a projekty zůstat řízené.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)