---
title: 'Chyba: Ladění se nezdařilo, protože integrované ověřování systému Windows není povoleno. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.webdbg_ntlm_authn_not_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
- aspx
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7181642b0a1f05a3eae252393e8daeefe5947d05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-debugging-failed-because-integrated-windows-authentication-is-not-enabled"></a>Chyba: Ladění se nezdařilo, protože integrované ověřování systému Windows není povoleno.
Ověření uživatele, který požadovaný ladění zabránily chyby ověřování. Tato situace může nastat, když zkusíte krok do webové aplikace nebo webové služby XML. Jeden příčinu této chyby je, že integrované ověřování systému Windows není povoleno. Ho Pokud chcete zapnout, postupujte podle kroků v "K povolení integrované ověřování systému Windows."  
  
 Pokud jste povolili integrované ověřování systému Windows a tato chyba, je stále zobrazena, je možné, že tato chyba se nezdařila, protože **Digest ověřování pro doménové servery Windows** je povoleno. V této situaci, obraťte se na správce sítě.  
  
### <a name="to-enable-integrated-windows-authentication"></a>Chcete-li povolit integrované ověřování systému Windows  
  
1.  Přihlaste se k webovému serveru pomocí účtu správce.  
  
2.  Klikněte na tlačítko **spustit** a pak klikněte na **ovládací panely**.  
  
3.  V **ovládací panely**, dvakrát klikněte na **nástroje pro správu**.  
  
4.  Klikněte dvakrát na **Internetová informační služba**.  
  
5.  Klikněte na uzel webového serveru.  
  
     A **weby** složky otevře pod název serveru.  
  
6.  Můžete nakonfigurovat ověřování pro všechny weby nebo pro jednotlivé webové servery. Postup konfigurace ověřování pro všechny webové servery, klikněte pravým tlačítkem myši **weby** složku a pak klikněte na tlačítko **vlastnosti**. Chcete-li konfigurovat ověřování pro konkrétní webový server, otevřete **weby** složku, klikněte pravým tlačítkem na jednotlivé webu a pak klikněte na tlačítko **vlastnosti**.  
  
     **Vlastnosti** se zobrazí dialogové okno.  
  
7.  Klikněte **zabezpečení adresáře** kartě.  
  
8.  V **anonymního přístupu a ověřování** klikněte na tlačítko **upravit**.  
  
     **Metody ověřování** se zobrazí dialogové okno.  
  
9. V části **ověřeného přístupu**, vyberte **integrované ověřování systému Windows**.  
  
10. Klikněte na tlačítko **OK** zavřete **metody ověřování** dialogové okno.  
  
11. Klikněte na tlačítko **OK** zavřete **vlastnosti** dialogové okno.  
  
12. Zavřít **Internetová informační služba** okno.  
  
### <a name="to-enable-integrated-windows-authentication-in-windows-vistaiis-7"></a>Chcete-li povolit integrované ověřování systému Windows v systému Windows Vista nebo IIS 7  
  
1.  Přihlaste se k webovému serveru pomocí účtu správce.  
  
2.  Zapněte ověřování systému Windows a II6 Kompatibilita správy, pokud jste ještě dřív, pomocí následujících kroků:  
  
    1.  Klikněte na tlačítko **spustit**, klikněte na tlačítko **ovládací panely** a pak klikněte na **programy**.  
  
    2.  V části **programy a funkce**, klikněte na tlačítko **Windows zapnout nebo vypnout funkce**.  
  
         Dialogové okno řízení přístupu uživatelů se zobrazí a vás vyzve k zadání oprávnění pokračujte.  
  
    3.  Klikněte na tlačítko **pokračovat**.  
  
         Zobrazí se dialogové okno funkce systému Windows.  
  
    4.  V seznamu funkcí, rozbalte **Internetová informační služba** uzlu.  
  
    5.  V části **Internetová informační služba**, rozbalte **webové služby** uzlu.  
  
    6.  V části **webové služby**, klikněte na tlačítko **zabezpečení**.  
  
    7.  Klikněte na tlačítko **ověřování systému Windows**.  
  
    8.  V části **Internetová informační služba**, rozbalte **nástroje webové správy** uzlu.  
  
    9. V části **nástroje webové správy**, rozbalte **IIS 6 Management Compatibility** uzel a vyberte možnost **metabáze služby IIS 6 a kompatibilita konfigurace služby IIS 6** zaškrtávací políčko.  
  
    10. V části **nástroje webové správy**, vyberte **konzoly pro správu služby IIS** a klikněte na tlačítko **OK.**  
  
    11. Po restartování počítače tyto změny se projeví.  
  
3.  Klikněte na tlačítko **spustit** a potom klikněte na **ovládací panely**.  
  
4.  Klikněte na tlačítko **klasickém zobrazení**a potom dvakrát klikněte na **nástroje pro správu**.  
  
5.  V **název** sloupce a poklikejte na soubor **Správce Internetové informační služby (IIS)**.  
  
6.  V **připojení** sloupce, rozbalte uzel serveru.  
  
     A **weby** složky otevře pod název serveru.  
  
7.  Rozbalte **weby** uzel a klikněte na web, pro který chcete povolit integrované ověřování systému Windows.  
  
8.  Název v prostředním podokně se změní na název webu, který jste vybrali. V tomto podokně v části **IIS** záhlaví, klikněte dvakrát na **ověřování**.  
  
     Název v podokně se změní na **ověřování**.  
  
9. V **ověřování** podokně, v **název** sloupce, klikněte pravým tlačítkem na **ověřování systému Windows** a pak klikněte na **povolit**.  
  
10. Zavřít **Správce Internetové informační služby (IIS)** okno.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [Ověřování hodnotou hash Microsoft](http://go.microsoft.com/fwlink/?LinkId=77938)   
 [Spouštění webových aplikací v systému Windows Vista se službou IIS 7.0 a Visual Studio](http://msdn.microsoft.com/Library/262a82ac-dd0e-4096-86c6-fb463e88be66)