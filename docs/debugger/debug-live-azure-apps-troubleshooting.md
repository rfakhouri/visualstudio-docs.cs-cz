---
title: "Řešení potíží a známé problémy pro ladění snímku | Microsoft Docs"
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d007bdf5d2029e896167a2fd7b32359c661aa7fa
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Řešení potíží a známé problémy pro snímek ladění v sadě Visual Studio

Pokud kroků popsaných v tomto tématu váš problém nevyřeší, obraťte se na snaphelp@microsoft.com.

## <a name="issue-snappoint-does-not-turn-on"></a>Problém: Snappoint nezapne

Pokud se zobrazí ikona upozornění ![ikona upozornění Snappoint](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "ikona upozornění Snappoint") s vaší snappoint místo ikonu regulární snappoint, pak snappoint není zapnutý.

![Snappoint nezapne](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint nezapne")

Proveďte tyto kroky:

1. Zkontrolujte, zda že máte stejnou verzi nástroje zdrojového kódu, která se použila k vytvoření a nasazení vaší app.isua1. Ujistěte se, že při zavádění správné symboly pro vaše nasazení. Chcete-li to provést, podívejte se **moduly** okno při ladění snímku a ověřte souboru se symboly sloupci se zobrazuje soubor .pdb načíst pro modul, kterou ladíte. Poznámka: ladicí program snímku se pokusí automaticky stáhnout a použít symboly pro vaše nasazení.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>Problém: Symboly se nenačtou při otevření snímku

Pokud se zobrazí následující okno, nenačetl se symboly.

![Symboly se nenačtou](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "symboly nenačítají.")

Proveďte tyto kroky:

- Klikněte **změnit Symbol nastavení...** odkaz na této stránce. V **ladění > Symbol** nastavení, přidejte adresář mezipaměti symbol. Restartujte snímku ladění po cestu symbolů.

   Nasazení služby App Service musí odpovídat symboly nebo soubory PDB, k dispozici ve vašem projektu. Většina nasazení (nasazení pomocí sady Visual Studio, CI/CD s služby VSTS nebo Kudu, atd.) bude publikovat vaše soubory symbolů podél do vaší služby App Service. Nastavení složky mezipaměti symbol umožňuje sadě Visual Studio pro použití těchto symbolů.

   ![Symbolů nastavení](../debugger/media/snapshot-troubleshooting-symbol-settings.png "symbolů nastavení")

- Pokud vaše organizace používá symbol server nebo zahodí symboly v jiné cestě, použijte nastavení symbol načíst správné symboly pro vaše nasazení.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>Problém: nelze zobrazit možnosti "Připojit snímek ladicí program" v Průzkumníku cloudu

Proveďte tyto kroky:

- Zkontrolujte, zda že je nainstalována součást snímku ladicí program. Spusťte instalační program Visual Studio a zkontrolujte **ladicí program snímku** součásti v Azure zatížení.
- Ujistěte se, že aplikace je podporována. V současné době pouze technologii ASP.NET (4.6.1+) a ASP.NET Core (2.0 +) aplikace nasazené na Azure App Services podporované.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>Problém: zobrazena pouze omezeny snímky v okně diagnostické nástroje

![Throttled snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "omezeny snappoint")

Proveďte tyto kroky:

- Snímky trvat velmi málo paměti, ale máte potvrzení poplatků. Pokud snímek ladicí program zjistí, že je server zatížen velkou paměť, nebude snímky. Odstraněním již zaznamenané snímky zastavování relace ladicí program snímek a opakujte akci.

## <a name="known-issues"></a>Známé problémy

- Ladění snímku s více klienty sady Visual Studio proti stejné služby App Service není aktuálně podporován.
- Optimalizace Roslyn IL nejsou plně podporovány projektů ASP.NET Core. U některých projektů ASP.NET Core nemusí být možné najdete některé proměnné a používat některé proměnné v podmíněné příkazy. 
- Speciální proměnné, jako například *$FUNCTION* nebo *$CALLER*, nelze vyhodnotit v podmíněné příkazy nebo logpoints pro projekty ASP.NET Core.
- Ladění snímku nefunguje na aplikační služby, které mají [místní ukládání do mezipaměti](/azure/app-service/app-service-local-cache) zapnutý.
- Ladění aplikace API snímku není aktuálně podporován.

## <a name="see-also"></a>Viz také

[Ladění v sadě Visual Studio](../debugger/index.md)  
[Ladění za provozu aplikace ASP.NET pomocí snímku ladicí program](../debugger/debug-live-azure-applications.md)  
[Nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md)  
