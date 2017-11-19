---
title: "Nativní Run-Time kontroluje přizpůsobení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.crt
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- runtime_checks pragma
- debugger, native run-time checks
- /RTC compiler option [C++], native run-time checks
- customizing CRT error checking
- native run-time checks, customizing
ms.assetid: 76a365fe-6439-49db-8603-34058b78e5a8
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da047f9739fc8af1c12fc084df4ef5a267192656
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="native-run-time-checks-customization"></a>Přizpůsobení nativních kontrol za běhu
Když kompilujete s **/RTC** (spuštění kontroly) nebo pomocí `runtime_checks` – Direktiva pragma, běhové knihovny jazyka C poskytuje nativních kontrol za běhu. V některých případech můžete chtít přizpůsobit spuštění kontroly:  
  
-   Kontrola běhu zprávy směrovat k souboru nebo cílové jiné než výchozí.  
  
-   Chcete-li určit výstup cíl pro spuštění zkontrolujte zprávy v rámci ladicí program třetí strany.  
  
-   Tak, aby odesílaly zprávy kontrola běhu z programu kompilovat s prodejní verze nástroje běhové knihovny jazyka C. Verze knihovny nepoužívejte `_CrtDbgReportW` chyby spuštění sestavy. Místo toho, které se zobrazuje **Assert** dialogové okno pro každou chybu spuštění.  
  
 Chcete-li přizpůsobit Kontrola chyb za běhu, můžete:  
  
-   Chyba při spuštění funkce vytváření sestav zápisu Další informace najdete v tématu [postupy: zápis funkce Reporting chyba Run-Time](../debugger/how-to-write-a-run-time-error-reporting-function.md).  
  
-   Přizpůsobte chyba cíl zprávy.  
  
-   Dotaz na informace o běhu informacích o chybě.  
  
## <a name="customize-the-error-message-destination"></a>Přizpůsobení cíl zprávy chyby  
 Pokud používáte `_CrtDbgReportW` zprávy o chybách, můžete použít `_CrtSetReportMode` zadat cíl chybové zprávy.  
  
 Pokud používáte vlastní funkci vytváření sestav, použijte `_RTC_SetErrorType` pro přidružení k chybě typu sestavy.  
  
## <a name="query-for-information-about-run-time-checks"></a>Dotaz na informace o kontroly runtime  
 `_RTC_NumErrors`Vrátí počet typů chyb zjištěný Kontrola chyb za běhu. Získat stručný popis každé chybě, můžete opakování od 0 do návratová hodnota `_RTC_NumErrors`, předávání iterace hodnota, která má `_RTC_GetErrDesc` na každou smyčku. Další informace najdete v tématu [_rtc_numerrors –](/cpp/c-runtime-library/reference/rtc-numerrors) a [_rtc_geterrdesc –](/cpp/c-runtime-library/reference/rtc-geterrdesc).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití nativních kontrol za běhu](../debugger/how-to-use-native-run-time-checks.md)   
 [runtime_checks –](/cpp/preprocessor/runtime-checks)   
 [_Crtdbgreport –, _crtdbgreportw –](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)