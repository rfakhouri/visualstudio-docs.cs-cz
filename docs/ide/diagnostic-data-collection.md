---
title: Diagnostická data a systémem generovaných protokolů
ms.date: 05/24/2018
ms.topic: conceptual
author: gewarren
ms.author: michma
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f92e899ff8e56c68fcf1a4ab639d027c139afcf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55925487"
---
# <a name="system-generated-logs-collected-by-visual-studio"></a>Systémem generovaných protokolech shromažďovaných sady Visual Studio

Shromažďuje protokoly generované systémem k řešení potíží a zlepšování kvality produktu prostřednictvím sady Visual Studio [programu Visual Studio Customer Experience Improvement](visual-studio-experience-improvement-program.md). Tento článek obsahuje některé informace o typech dat, které shromažďujeme a jak ho použít. Také poskytuje tipy, jak autoři rozšíření můžete zabránit neúmyslnému zveřejnění osobní nebo důvěrné informace.

## <a name="types-of-collected-data"></a>Typy shromážděných dat

Visual Studio shromažďuje protokoly generované systémem pro chyby, přestane reagovat, zablokování uživatelského rozhraní a vysoké využití procesoru nebo paměti. Můžeme také shromažďovat informace o chybách během instalace produktu nebo využití. Shromážděná data se liší v závislosti na chybu a mohou zahrnovat informace o výjimce, trasování zásobníku a výpisy paměti:

- Vysoké využití procesoru a sekundový výpadek reakce se shromáždí trasování zásobníku vlákna relevantní sady Visual Studio.

- Pro případy, kdy trasování zásobníku z některá vlákna nejsou dost informací k určení kořenové příčiny problému, například selhání, zablokování nebo vysoké využití paměti, můžeme shromažďovat paměťově *s výpisem paměti*. Výpis představuje stav procesu, když došlo k chybě.

- Došlo k neočekávané chybě podmínky, například výjimku při pokusu o zápis do souboru na disku, můžeme shromažďovat informace o výjimce. Informace zahrnují název výjimky, trasování zásobníku pro vlákno, ve kterém k výjimce došlo, zprávy související s výjimkou a další informace relevantní pro určité výjimky.

   Následující příklad shromážděných dat ukazuje název výjimky, trasování zásobníku a zpráva o výjimce:

   ```text
   "Reserved.DataModel.Fault.Exception.TypeString": "System.IO.IOException",
   "Reserved.DataModel.Fault.Exception.StackTrace": "System.IO.__Error.WinIOError(Int32,String)\r\n
   System.IO.FileStream.Init(String,FileMode,FileAccess,Int32,Boolean,FileShare,Int32,FileOptions,SECURITY_ATTRIBUTES,String,Boolean,Boolean,Boolean)\r\n
   System.IO.FileStream..ctor(String,FileMode,FileAccess,FileShare,Int32,FileOptions,String,Boolean,Boolean,Boolean)\r\nSystem.IO.StreamWriter.CreateFile(String,Boolean,Boolean)\r\n
   System.IO.StreamWriter..ctor(String,Boolean,Encoding,Int32,Boolean)\r\n
   System.IO.StreamWriter..ctor(String,Boolean)\r\n
   System.IO.File.CreateText(String)\r\n
   Microsoft.VisualStudio.Setup.Services.FileSystem.CreateText(String,Boolean)\r\n
   Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository.WriteChannelManifest(IChannelManifest,String,String)\r\n
   Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository.AddChannel(ChannelManifestPair,Boolean)\r\n
   Microsoft.VisualStudio.Setup.Cache.CacheManager.AddChannel(ChannelManifestPair,Boolean)\r\n
   Microsoft.VisualStudio.Setup.ChannelManager.\<UpdateAsync>d__37.MoveNext()\r\n”,
   "Reserved.DataModel.Fault.Exception.Message": " The process cannot access the file 'C:\\Users\\[UserName]\\AppData\\Local\\Microsoft\\VisualStudio\\Packages\\_Channels\\4CB340F5\\channelManifest.json' because it is being used by another process."
   ```

## <a name="how-we-use-system-generated-logs"></a>Jak používáme systémem generovaných protokolů

Pracovní postup k určení příčiny chyby se liší v závislosti na typu chyby a závažnosti.

### <a name="error-classification"></a>Chyba klasifikace

Podle protokolů, jsou chyby klasifikovány a počítá k určení priority jejich šetření. Například může zjistíme tento "System.IO. \__Error.WinIOError "na"System.IO.FileStream.Init"došlo k 500 x ve verzi \<x > produktu, a má nejvyšší počet výskytů v této verzi.

### <a name="work-items-for-tracking"></a>Pro sledování pracovních položek

Pracovní položky chyby jednotlivých, seřazený podle priority jsou vytvořené a přiřazeno technikům pro šetření. Tyto pracovní položky obvykle obsahují klasifikace, priority a diagnostické informace, které jsou relevantní pro typ chyby. Tyto informace je odvozen ze shromážděných systémem generovaných protokolů pro chybu. Pracovní položku pro selhání může například obsahovat trasování zásobníku, kde dochází k selhání.

### <a name="error-investigation"></a>Chyba šetření

Pracovníci používají informace, které jsou k dispozici v pracovní položce určit hlavní příčinu chyby. V některých případech se potřebují další informace, než co je k dispozici v pracovní položce, v takovém případě odkazují na původní protokol generované systémem, která byla shromážděna. Pracovník může například zkontrolovat výpis paměti pochopit selhání produktu.

## <a name="tips-for-extension-authors"></a>Tipy pro autory rozšíření

Autoři rozšíření by měl omezení rizika ohrožení osobní údaje bez použití osobní a dalších citlivých údajů v názvech svých modulů, typů a metod. Pokud s tímto kódem v zásobníku dojde k selhání nebo podobná chybová podmínka, tyto informace získá shromažďuje jako součást systémem generovaných protokolů.

## <a name="opt-out-of-data-collection"></a>Odhlásit ze shromažďování dat

Zadaný účel data, která shromažďujeme a omezení na jeho přístup a uchovávání dat, doporučujeme použít výchozí nastavení ochrany osobních údajů pro Visual Studio a Windows. Můžete však [Odhlásit se totiž](../ide/visual-studio-experience-improvement-program.md#opt-in-or-out) z programu zlepšování sady Visual Studio prostředí. Chcete-li odhlásit ze shromažďování systémem generovaných protokolů pro všechny programy, přečtěte si téma [diagnostiky, zpětnou vazbu a ochrana osobních údajů ve Windows 10](https://privacy.microsoft.com/windows-10-feedback-diagnostics-and-privacy). Možnosti se mohou lišit v závislosti na verzi Windows, které používáte.

## <a name="see-also"></a>Viz také:

- [Program Zlepšování softwaru a služeb na základě zkušeností uživatelů](visual-studio-experience-improvement-program.md)
- [Diagnostika, zpětnou vazbu a ochrana osobních údajů ve Windows 10](https://privacy.microsoft.com/windows-10-feedback-diagnostics-and-privacy)