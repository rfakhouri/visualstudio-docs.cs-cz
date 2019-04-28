---
title: Nativní Run-Time kontroluje přizpůsobení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.crt
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 66591308c2b0c59cf310d3957131f80191cc51c3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62905483"
---
# <a name="native-run-time-checks-customization"></a>Přizpůsobení nativních kontrol za běhu
Pokud kompilujete s **/RTC** (kontroly za běhu) nebo použít `runtime_checks` – Direktiva pragma, knihovny run-time jazyka C poskytuje nativní kontroly za běhu. V některých případech můžete chtít přizpůsobit kontrolu za běhu:

- Můžete směrovat zprávy kontrola běhu soubor nebo cíl jiné než výchozí.

- K určení výstupní cíl pro za běhu kontrolovat zprávy v ladicím programu třetích stran.

- K hlášení kontroly za běhu z programu kompilovaného s verzi knihovny run-time C. Verze knihovny nepoužívejte `_CrtDbgReportW` pro hlášení chyb za běhu. Zobrazí se místo toho **Assert** dialogové okno u každé chyby za běhu.

  Chcete-li přizpůsobit, kontrola chyb za běhu, můžete:

- Zápis chyb za běhu funkce vytváření sestav. Další informace najdete v tématu [jak: Zápis Run-Time chybách funkce](../debugger/how-to-write-a-run-time-error-reporting-function.md).

- Upravte cíl chybové zprávy.

- Dotaz na informace o běhu najdete v chybách.

## <a name="customize-the-error-message-destination"></a>Upravit cíl chybové zprávy
 Pokud používáte `_CrtDbgReportW` pro hlášení chyb, můžete použít `_CrtSetReportMode` k určení cíle chybové zprávy.

 Pokud používáte vlastní funkci vykazování, použijte `_RTC_SetErrorType` chcete přidružit k chybě typu sestavy.

## <a name="query-for-information-about-run-time-checks"></a>Dotaz na informace o kontrolách za běhu
 `_RTC_NumErrors` Vrátí počet typů chyb zjištěných kontroly chyb za běhu. Získáte stručný popis jednotlivých chyb můžete opakování od 0 do návratová hodnota `_RTC_NumErrors`, předejte hodnotu iterace k `_RTC_GetErrDesc` na každou smyčku. Další informace najdete v tématu [_rtc_numerrors –](/cpp/c-runtime-library/reference/rtc-numerrors) a [_RTC_GetErrDesc](/cpp/c-runtime-library/reference/rtc-geterrdesc).

## <a name="see-also"></a>Viz také
- [Postupy: Použití nativních kontrol za běhu](../debugger/how-to-use-native-run-time-checks.md)
- [runtime_checks](/cpp/preprocessor/runtime-checks)
- [_CrtDbgReport, _CrtDbgReportW](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)