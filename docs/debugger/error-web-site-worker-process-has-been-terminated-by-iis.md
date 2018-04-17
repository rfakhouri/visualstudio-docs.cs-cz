---
title: 'Chyba: pracovní proces webu byl ukončen službou IIS | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.web_server_process_terminated
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f7f4719cb1ea48eb8ecb896fc0a404aa1759a24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>Chyba: Pracovní proces webu byl ukončen službou IIS.
Ladicí program zastavena spuštění kódu na webovém serveru. Příčinou Internetové informační služby (IIS) předpokládají, že měl pracovní proces přestal reagovat. Proto služba IIS byla ukončena pracovního procesu.  
  
 Chcete-li pokračovat, ladění, je nutné nakonfigurovat služby IIS umožňující pracovního procesu pokračovat. Tato chybová zpráva se nezobrazí s verzemi služby IIS, která jsou starší než IIS 7.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>Ke konfiguraci služby IIS 7 umožňuje pracovního procesu pokračovat  
  
1.  Otevřete **nástroje pro správu** okno.  
  
    1.  Klikněte na tlačítko **spustit**a potom zvolte **ovládací panely**.  
  
    2.  V **ovládací panely**, zvolte **přepnout do klasického zobrazení**, v případě potřeby a potom dvakrát klikněte na **nástroje pro správu**.  
  
2.  V **nástroje pro správu** okna, klikněte dvakrát na **Správce Internetové informační služby (IIS)**.  
  
     Otevře se Správce služby IIS.  
  
3.  V **připojení** podokně rozbalte \<název počítače > uzlu v případě potřeby.  
  
4.  V části \<název počítače > uzel, klikněte na tlačítko **fondy aplikací**.  
  
5.  V **fondy aplikací** seznamu, klikněte pravým tlačítkem na název vaší aplikace běží ve fondu a pak klikněte na tlačítko **Upřesnit nastavení**.  
  
6.  V **Upřesnit nastavení** dialogové okno pole, vyhledejte **Model procesu** části a proveďte jednu z následujících akcí:  
  
    -   Nastavit **Ping povoleno** k **False**.  
  
    -   Nastavit **maximální dobu odezvy příkazu Ping** na hodnotu, která je větší než 90 sekund.  
  
     Nastavení **Ping povoleno** k **False** zastaví od kontroly, zda pracovní proces je stále spuštěná a zachová pracovní proces aktivní, dokud jej nezastavíte váš vyladěnou proces služby IIS. Nastavení **maximální dobu odezvy příkazu Ping** velké hodnoty umožňuje Internetové informační službě pokračovat v monitorování pracovního procesu.  
  
7.  Klikněte na tlačítko **OK** zavřete **Upřesnit nastavení** dialogové okno.  
  
8.  Zavřete Správce služby IIS a **nástroje pro správu** okno.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)