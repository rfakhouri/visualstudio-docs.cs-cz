---
title: Omezení ladění WCF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7696afd789753b85facf44dfeadf1f3f30c1596b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="limitations-on-wcf-debugging"></a>Omezení ladění WCF
Existují tři způsoby, můžete začít ladění služby WCF:  
  
-   Ladění procesu klienta, který volá služby. Ladicí program do služby. Služba nemusí být ve stejném řešení jako klientské aplikace.  
  
-   Ladění procesu klienta, který odešle požadavek služby. Služba musí být součástí vašeho řešení.  
  
-   Používáte **připojit k procesu** pro připojení k službě, která je aktuálně spuštěna. Ladění začne uvnitř službu.  
  
 Toto téma popisuje omezení pro tyto scénáře.  
  
## <a name="limitations-on-stepping-into-a-service"></a>Omezení Zanoříte se do služby  
 Pro krok do služby z klientských aplikací, které jsou ladění, musí být splněny následující podmínky:  
  
-   Klient musí volat službu pomocí objektu synchronní klienta.  
  
-   Operaci smlouvy nesmí být jednosměrná.  
  
-   Pokud je server asynchronní, nelze zobrazit zásobníku volání úplné průběhu jsou provádění kódu do služby.  
  
-   Následující kód v souboru Web.config nebo app.config musí být povoleno ladění:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    </system.web>  
    ```  
  
     Tento kód jenom musí být přidán jednou. Tento kód můžete přidat, a to úpravou souboru .config nebo připojením ke službě pomocí **připojit k procesu**. Při použití **připojit k procesu** službu, ladění kódu se automaticky přidá do souboru .config. Potom můžete ladit a krok do služby, aniž by bylo nutné upravit soubor .config.  
  
## <a name="limitations-on-stepping-out-of-a-service"></a>Omezení krokování s mimo službu  
 Krokování s mimo službu a zpět do klienta má stejné omezení popsané pro zanoříte se do služby. Ladicí program kromě toho musí být připojené ke klientovi. Pokud ladíte klienta a krokování s vnořením služby, zůstane připojený ke službě ladicího programu. Toto je hodnota true, jestli jste spustili klienta pomocí **spustit ladění** nebo připojené ke klientovi pomocí **připojit k procesu**. Pokud jste začali ladění připojením ke službě, není dosud připojen ladicí program klientovi. V takovém případě Pokud máte k kroku mimo službu a zpět do klienta, musíte nejprve použít **připojit k procesu** pro připojení k klienta ručně.  
  
## <a name="limitations-on-automatic-attach-to-a-service"></a>Omezení automatické připojení ke službě  
 Automaticky se připojuje ke službě má následující omezení:  
  
-   Služba musí být součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, kterou ladíte.  
  
-   Musí být hostované služby. To může být součástí webový projekt (systém souborů a HTTP), projekt webové aplikace (systém souborů a HTTP) nebo projekt knihovny služby WCF. Projekty knihovny služby WCF může být služba knihovny nebo knihovny služby pracovního postupu.  
  
-   Služba musí být volána z klienta WCF.  
  
-   Následující kód v souboru Web.config nebo app.config musí být povoleno ladění:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    <system.web>  
    ```  
  
## <a name="self-hosting"></a>Vlastní hostování  
 A *hostovanou na vlastním* je služba WCF, která není spuštěna v IIS, hostitel služby WCF, nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] vývojový Server. Informace o tom, jak ladění služby s vlastním hostováním najdete v tématu [postupy: ladění služby WCF s Self-Hosted](../debugger/how-to-debug-a-self-hosted-wcf-service.md).  
  
## <a name="self-hosting"></a>Vlastní hostování  
 Chcete povolit ladění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace 3.0 nebo 3.5 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 nebo 3.5 musí být nainstalována před [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] je nainstalovaná. Pokud [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] nainstalovali před [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 nebo 3.5, dojde k chybě při pokusu o ladění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace 3.0 nebo 3.5. Je chybová zpráva "nelze automaticky krok do serveru." Chcete-li tento problém vyřešit, použijte Windows **ovládací panely** > **programy a funkce** k opravě vaší [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] instalace.  
  
## <a name="see-also"></a>Viz také  
 [Ladění služby WCF](../debugger/debugging-wcf-services.md)   
 [Postupy: ladění služby WCF s vlastním hostováním](../debugger/how-to-debug-a-self-hosted-wcf-service.md)