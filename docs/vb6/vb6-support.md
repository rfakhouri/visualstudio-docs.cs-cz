---
title: "Podpora příkaz jazyka Visual Basic 6.0 | Microsoft Docs"
ms.date: 08/28/2017
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs: VB
helpviewer_keywords:
- VB6 support
- Visual Basic 6.0 support
ms.assetid: ffc5ba4d-44d7-4ef7-a3f6-38a8738bf127
author: paulyuk
ms.author: paulyuk
ms.openlocfilehash: bdfe33cac19d488bc7763f3c61c518093d8afffa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="support-statement-for-visual-basic-60-on-windows"></a>Podpora příkaz jazyka Visual Basic 6.0 v systému Windows


## <a name="executive-summary"></a>Shrnutí

Týmem jazyka Visual Basic je potvrzena pro "Prostě to funguje" kompatibilitu aplikací Visual Basic 6.0 na následujících podporovaných operačních systémech Windows: 

- Windows 10
- Windows 8.1
- Windows 7
- Windows Server 2016
- Windows Server 2012 R2 včetně
- Windows Server 2008 R2 včetně

Tým jazyka Visual Basic cílem je, že aplikace Visual Basic 6.0 dál běžet podporované verze systému Windows. Podle popisu v tomto dokumentu budou na Visual Basic 6.0 core runtime podporované pro úplné životnost podporované verze systému Windows, což je pět let všeobecně podporovaných následuje pět let rozšířené podpory (http://support.microsoft.com/gp/lifepolicy). Na panelu podporu bude omezeno na závažnou regresí a problémy se zabezpečením kritické pro existující aplikace.

## <a name="technical-summary"></a>Technické souhrn

Visual Basic 6.0 se skládá z těchto hlavní dodávky:
- Visual Basic 6.0 IDE (integrované vývojové prostředí).
- Modul Runtime jazyka Visual Basic 6.0: základní knihovny a modul pro spuštění používá ke spouštění aplikací jazyka Visual Basic 6.0.
- Soubory Extended modulu Runtime jazyka Visual Basic 6.0: vybrané soubory OCX ovládací prvek ActiveX, knihovny a nástroje přesouvání s médii nástroje IDE a jako online verzi.

## <a name="the-visual-basic-60-ide"></a>Visual Basic 6.0 IDE

Integrovaného vývojového prostředí jazyka Visual Basic 6.0 se už nepodporuje od 8. dubna 2008. Kromě toho Windows i jazyka Visual Basic týmy otestovali IDE Visual Basic 6.0 na Windows Vista, Windows 7, Windows Server 2008, Windows 8 a Windows 8.1 pochopit a zmírnit (v případě potřeby) problémy s kompatibilitou na 32bitové verze systému Windows (viz [64bitová verze Windows](#62-bit-windows) části níže Další informace o systémech 64-bit). Tato oznámení se nemění zásady podpory pro rozhraní IDE.

## <a name="the-visual-basic-60-runtime"></a>Modul runtime jazyka Visual Basic 6.0

Modul runtime jazyka Visual Basic 6.0 je definován jako zkompilované binární soubory původně součástí seznam Redistribuce pro Visual Basic 6.0. Tyto soubory byly označeny jako distribuovatelného v původní licenci Visual Basic 6.0. Příklady těchto souborů běhové knihovny jazyka Visual Basic 6.0 (`msvbvm60.dll`), ovládací prvky (tj, `msflxgrd.ocx`) společně s runtime podpůrné soubory pro další hlavní funkčním oblastem (tj. MDAC).

Modul runtime je rozdělené do tří skupin:

- Podporované soubory modulu runtime – přesouvání v operačního systému

   Soubory modulu runtime Visual Basic 6.0 klíč, použít ve většině scénářů aplikace jsou v přesouvání a podporované po dobu jeho existence podporované verze systému Windows. Tato doba platnosti je pět let všeobecně podporovaných a pět let rozšířené podpory od času, který se dodává s danou verzí systému Windows. Tyto soubory byly testovány z hlediska kompatibility jako součást našich testech Visual Basic 6.0 aplikací běžících na podporované verze systému Windows. 

   > [!NOTE]
   > Všechny podporované verze systému Windows obsahovat téměř shodná seznam souborů a požadavky na redistribuci aplikací obsahující tyto soubory by měly být téměř shodné. Jeden klíčovým rozdílem je, že `TriEdit.dll` byla odebrána ze systému Windows Vista a novějších verzích.

- Podporované soubory modulu runtime –-rozšířené soubory k distribuci s vaší aplikací

   Tento rozšířený seznam se skládá z klíče ovládací prvky, knihovny a nástroje, které jsou nainstalované z média IDE nebo z webu Microsoft.com k počítači vývojáře. VB6 IDE obvykle nainstalovány tyto ovládací prvky pro vývojáře počítače ve výchozím nastavení. Vývojář se ještě potřeba znovu distribuovat tyto soubory s aplikací. Podporovaná verze systému souborů je k dispozici online na webu Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkID=142927).

- Soubory modulu runtime nepodporované

   Některé soubory, které mají buď z všeobecná odstraněn podporu nebo nikdy byly zahrnuty jako součást runtime redist (například byly zahrnuté v `\Tools` složky na IDE médium pro podporu starších verzí aplikací VB4/VB5, nebo byly ovládací prvky třetích stran). Tyto soubory nejsou podporovány v systému Windows; Místo toho jsou předmětem ať dohoda podpora se vztahuje na médium, které byly dodány s. To znamená žádné výslovné záruky ohledně podpory a údržby. V některých případech jsou podporovány tyto knihovny novější verze. Podrobnosti o zpětné kompatibility nebo migraci podporované verze jsou uvedeny níže.

Konkrétní podrobnosti na soubory obsažené v každé skupině podpory najdete v tématu [definice modulu Runtime](#runtime-definition) části níže.

## <a name="the-visual-basic-60-support-lifetime"></a>Doba platnosti podporu jazyka Visual Basic 6.0

Podpora nebo přesouvání binární soubory modulu runtime Visual Basic 6.0 na podporované verze systému Windows se nemění zásady podpory pro Visual Studio 6.0 IDE na Visual Basic 6.0 IDE jako celek. Tyto produkty přesunout mimo rozšířené podpory na 8. dubna 2008.

Podrobnosti o životní cyklus podpory produktů společnosti Microsoft naleznete na http://support.microsoft.com/gp/lifepolicy. Jako součást tohoto životního cyklu podpory Microsoft dál podporovat runtime jazyka Visual Basic 6.0 na podporované verze systému Windows pro životního cyklu podpory těchto operačních systémů. To znamená, například, že modul runtime jazyka Visual Basic 6.0 budou podporované v systému Windows Server 2003 až do června, 2008 pro všeobecná podpora a červen 2013 pro rozšířené podpory.
Další podrobnosti na životní cyklus podpory nebo informace o další možnosti podpory navštivte naše stránky podpory v http://www.microsoft.com/support.

## <a name="64-bit-windows"></a>64bitová verze Windows

Soubory modulu runtime Visual Basic 6.0 se 32-bit. Tyto soubory jsou v 64bitových operačních systémech Windows odkazovaná v následující tabulce. v prostředí emulace WOW pouze se nepodporuje 32bitové VB6 aplikace a součásti. 32bitová verze součásti musí být také hostované v procesech 32bitovou aplikaci.

Integrovaného vývojového prostředí jazyka Visual Basic 6.0 nabízí nikdy v nativní 64bitové verze, ani se IDE 32-bit podporoval na 64bitovém systému Windows. Vývoj VB6 na 64bitovém systému Windows nebo všechny nativní architekturu než 32-bit není a již nebude podporována.

## <a name="windows-7"></a>Windows 7

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operační systém Windows 7. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 na systému Windows 7.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows 7 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci.

## <a name="windows-81"></a>Windows 8.1

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operační systém Windows 8.1. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 na Windows 8.1.

Modul runtime VB6 bude dodávat a budou podporované v Windows 8.1 pro dobu životnosti operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows 8.1, že je stejná jako je pro systém Windows 7.

## <a name="windows-10"></a>Windows 10

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operačním systémem Windows 10. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 ve Windows 10.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows 10 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows 10, že je stejná jako je pro Windows 8.1.

## <a name="windows-server-2008"></a>Windows Server 2008

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operační systém Windows Server 2008. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 v systému Windows Server 2008.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows Server 2008 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci.

## <a name="windows-server-2008-r2"></a>Windows Server 2008 R2

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operačního systému Windows Server 2008 R2. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 na Windows Server 2008 R2.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows Server 2008 R2 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows Server 2008 R2, že je stejná jako je Windows Server 2008.

## <a name="windows-server-2012"></a>Windows Server 2012

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operační systém Windows Server 2012. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 ve Windows serveru 2012.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows Server 2012 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows Server 2012, že je stejná jako je pro Windows Server 2008 R2.

## <a name="windows-server-2012-r2"></a>Windows Server 2012 R2

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operačního systému Windows Server 2012 R2. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 v systému Windows Server 2012 R2.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows Server 2012 R2 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows Server 2012 R2, že je stejná jako je pro Windows Server 2012.

## <a name="windows-server-2016"></a>Windows Server 2016

Od počáteční verze toto prohlášení o odborné pomoci byla vydána operačního systému Windows Server 2016. Tento dokument je aktualizovaná o vysvětlení, podpora společnosti Microsoft VB6 na Windows Server 2016.

Modul runtime VB6 bude odeslání a bude podporovaný v systému Windows Server 2016 po dobu jeho existence operačního systému. Soubory modulu runtime Visual Basic 6.0 nadále pouze být 32bitová verze a všechny součásti musí být hostované v procesech 32bitovou aplikaci. Vývojáři si můžete představit scénáře podpory pro Windows Server 2016, že je stejná jako je pro Windows Server 2012 R2.

## <a name="supported-windows-operating-system-versions"></a>Podporované verze operačního systému Windows

Tato část obsahuje další informace o operačních systémech, které nabízejí určité úrovně podpory pro VB6. 

|Operační systém Windows|VB6 Podporovaný modul Runtime</br>Soubory přesouvání v systému Windows mají podporu?|VB6 Podporované Rutime</br>Rozšířené soubory</br>k distribuci s vaší aplikací mít podporu?| VB6 IDE má podporu?|
|---|---|---|---|
|Windows 10, všechny 32-bit Edition|Ano *|Ano *|Ne|
|Windows 10, všechny 64-bit Edition (pouze WOW)|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows 8.1, všechny 32-bit Edition|Ano *|Ano *|Ne|
| Windows 8.1, všechny 64-bit Edition (pouze WOW)|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows 7, všechny 32-bit Edition|Ano *|Ano *|Ne|
|Windows 7, všechny 64-bit Edition (pouze WOW)|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows Server 2016, všechny 64-bit Edition (pouze WOW)|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows Server 2012 R2, všechny 64-bit Edition (pouze WOW)<br>Windows Server 2012, všechny 64-bit Edition (pouze WOW)|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ano* </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows Server 2008 R2, všechny x64 edice (pouze WOW)</br>Windows Server 2008, všechny x64 edice (pouze WOW)|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ano * </br> 32bitová verze aplikace běžící v WOW pouze|Ne|
|Windows Server 2008, všechny 32-bit Edition|Ano *|Ano *|Ne|


> [!NOTE]
> &#42;  Podpora modulu runtime VB6 je omezena životní cyklus podpory systému Windows.  Například pokud je cílový operační systém v rozšířené podpory, VB6 nemůže mít vyšší úroveň podpory než rozšířené podpory.  [Windows podporují životního cyklu fakt list](https://support.microsoft.com/en-us/help/13853/windows-lifecycle-fact-sheet) obsahuje životního cyklu Další informace o aktuální a předchozí verze Windows.

## <a name="visual-basic-60-runtime-usage-inside-vba-and-office"></a>Použití modulu runtime Visual Basic 6.0 uvnitř VBA a Office

Visual Basic pro aplikace nebo VBA pro vytváření, je odlišné technologie běžně používá pro aplikace automatizace a makra v rámci jiné aplikace, nejčastěji uvnitř aplikace Microsoft Office. VBA se dodává jako součást sady Office a proto se podpora pro jazyk VBA řídí zásady podpory Office. Existují však situacích, kdy je použít VBA zavolat nebo hostovat binární soubory modulu runtime Visual Basic 6.0 a ovládací prvky. V těchto situacích Visual Basic 6.0 podporované soubory modulu runtime operačního systému, a seznam rozšířených souborů jsou podporovány také při použití v rámci prostředí podporované VBA pro vytváření.

Pro scénáře runtime VB6 podporovaný uvnitř VBA pro vytváření musí být splněné všechny tyto:

- Verze operačního systému hostitele pro modul runtime jazyka Visual Basic je nadále podporován.
- Verze hostitele systému Office pro jazyk VBA se pořád podporuje.
- Soubory modulu runtime, která je nejistá jsou stále podporovány.

## <a name="visual-basic-script-vbscript"></a>Skript jazyka Visual Basic Script (VBScript)

VBScript nesouvisí s Visual Basic 6.0 a toto prohlášení o odborné pomoci. Ale VBScript aktuálně se dodává jako součást Windows 7, Windows 8.1, Windows 10, Windows Server 2008 R2, Windows Server 2012 R2 a Windows Server 2016 včetně včetně a se řídí životní cyklus podpory operačního systému.

## <a name="third-party-components"></a>Komponenty jiných výrobců

Společnost Microsoft se nepodařilo poskytnout podporu pro komponenty třetích stran, například OCX/ActiveX – ovládací prvky. Zákazníci se doporučuje požádejte o podrobnosti o podporu pro tyto součásti původní dodavatele ovládacího prvku.

## <a name="reporting-issues-with-vb-60-applications-running-on-windows"></a>Hlášení problémů s aplikacemi jazyka Visual Basic 6.0 se systémem Windows

Vývojáři v úmyslu používat Visual Basic 6.0 se jeden z uvedených operačních systémech Windows nainstalovat operačního systému a zahájit testování kompatibility aplikace pomocí původní testování přijetí aplikací.

Pokud zjistíte problém s vaší aplikací Visual Basic 6.0 spuštěn v jednom z uvedených operačních systémech Windows, postupujte podle pracovníkům podpory normální nahlásit problém.

## <a name="supported-and-shipping-in-windows"></a>Podporované a přenosů v systému Windows

| | | | |
|---|---|---|---|
|ATL.|         msadcor.dll|     MSORCL32.dll|   ole2.dll|
|Asycfilt.dll|    Msadcs.dll|      msvbvm60.dll|   Ole32.dll|
|comcat.dll|      knihovně MSADDS.dll|      Msvcirt.dll|    Oleaut32.dll|
|Knihovna compobj.dll|     msaddsr.dll|     Msvcrt.dll|     Oleaut32.dll|
|dbnmpntw.dll|    msader15.dll|    msvcrt40.dll|   Oledb32.dll|
|Dcomcnfg.exe|    Msado15.dll|     souboru Mtxdm.dll|      oledb32r.dll|
|Dllhost.exe|     Msador15.dll|    Mtxoci.dll|     oledlg.dll|
|ds16gt.dll|      msadrh15.dll|    odbc16gt.dll|   Olepro32.dll|
|ds32gt.dll|      mscpxl32.dll|    ODBC32.dll|     olethk32.dll|
|expsrv.dll|      Msdadc.dll|      odbc32gt.dll|   regsvr32.exe|
|hh.exe|          DLL knihovnu Msdaenum.dll|    Odbcad32.exe|   rpcns4.dll|
|Hhctrl.ocx|      msdaer.dll|      ODBCCP32.cpl|   Rpcrt4.dll|
|Imagehlp.dll|    MSDAORA.dll|     ODBCCP32.dll|   Scrrun.dll|
|iprop.dll|       msdaosp.dll|     Odbccr32.dll|   knihovnu Secur32.dll|
|Itircl.dll|      msdaprst.dll|    odbccu32.dll|   simpdata.tlb|
|Itss.dll|        msdaps.dll|      odbcint.dll|    SQLOLEDB.dll|
|mfc40.dll|       knihovna Msdasc.dll|      Odbcji32.dll|   Sqlsrv32.dll|
|Mfc42.dll|       MSDASQL.dll|     Odbcjt32.dll|   Stdole2.tlb|
|mfc42enu.dll|    msdasqlr.dll|    Odbctrac.dll|   stdole32.tlb|
|msadce.dll|      msdatsrc.tlb|    Oddbse32.dll|   Storage.dll|
|msadcer.dll|     msdatt.dll|      Odexl32.dll|    vbajet32.dll|
|msadcf.dll|      msdfmap.dll|     Odfox32.dll|    vfpodbc.dll|
|msadcfr.dll|     msdfmap.ini|     Odpdx32.dll|                |
|msadco.dll|      msjtes40.dll|    Odtext32.dll|               |

## <a name="supported-runtime-files-to-distribute-with-your-application"></a>Soubory podporované modulu runtime pro distribuci s vaší aplikací

| | | | |
|---|---|---|---|
|comct232.ocx |msbind.dll   |msdbrptr.dll  |soubor MSstdfmt.dll složky| 
|comct332.ocx |mscdrun.dll  |msflxgrd.ocx  |knihovny Msstkprp.dll| 
|Comctl32.ocx |Mschrt20.ocx |mshflxgd.ocx  |mswcrun.dll|  
|COMDLG32.ocx |mscomct2.ocx |mshtmpgr.dll  |Mswinsck.ocx| 
|dbadapt.dll  |MSCOMCTL.ocx |msinet.ocx    |picclp32.ocx| 
|dbgrid32.ocx |mscomm32.ocx |Msmapi32.ocx  |richtx32.ocx| 
|dblist32.ocx |msdatgrd.ocx |Msmask32.ocx  |sysinfo.ocx|  
|mci32.ocx    |msdatlst.ocx |msrdc20.ocx   |tabctl32.ocx| 
|msadodc.ocx  |msdatrep.ocx |Msrdo20.dll

## <a name="unsupported-but-supported-and-compatible-updates-or-upgrades-are-available"></a>Nepodporované, ale podporované a kompatibilní aktualizace nebo upgrady, které jsou k dispozici

| | | | |
|---|---|---|---|
|dao350.dll|   msexch35.dll| msjter35.dll| msrepl35.dll|
|Mdac_typ.exe| msexcl35.dll| msjtor35.dll| Mstext35.dll|
|MSChart.ocx|  msjet35.dll|  msltus35.dll| msxbse35.dll|
|msdaerr.dll|  msjint35.dll| Mspdox35.dll| odbctl32.dll|
|msdatl2.dll|  msjt4jlt.dll| msrd2x35.dll| oledb32x.dll|

## <a name="unsupported-runtime-files"></a>Soubory modulu runtime nepodporované

| | | | |
|---|---|---|---|
|anibtn32.ocx| spin32.ocx|   Rpcltscm.dll|  RDOCURS.dll|
|graph32.ocx|  gauge32.ocx|  rpcmqcl.dll|   vbar332.dll|
|keysta32.ocx| gswdll32.dll| rpcmqsvr.dll|  visdata.exe|
|autmgr32.exe| ciscnfg.exe|  Rpcss.exe|     vsdbflex.srg|
|autprx32.dll| Olecnv32.dll| dbmsshrn.dll|  threed32.ocx|
|racmgr32.exe| rpcltc1.dll|  Dbmssocn.dll|  MSWLess.ocx|
|racreg32.dll| rpcltc5.dll|  windbver.exe|  tlbinf32.dll|
|grid32.ocx|   Rpcltccm.dll| msderun.dll|   triedit.dll|
|msoutl32.ocx| rpclts5.dll|  odkob32.dll|

## <a name="localization-support-binaries"></a>Lokalizace podporu binárních souborů

Následující binární soubory jsou nezbytné pro podporu jazyka Visual Basic 6.0 aplikací běžících na lokalizované verze operačního systému Windows. Jsou podporována, ale nejsou součástí v systému Windows. Tyto soubory jsou muset být součástí instalace aplikace.

### <a name="supported-runtime-files-to-distribute-with-your-application"></a>Soubory podporované modulu runtime pro distribuci s vaší aplikací

|JPN|KOR|CHT|SADA CHS|
|---|---|---|---|
|mfc42jpn.dll|  mfc42kor.dll|  mfc42cht.dll|  mfc42chs.dll|
|scrrnjp.dll|   scrrnko.dll|   scrrncht.dll|  scrrnchs.dll|
|vb6jp.dll|     vb6ko.dll|     vb6cht.dll|    vb6chs.dll|
|cmct2jp.dll|   cmct2ko.dll|   cmct2cht.dll|  cmct2chs.dll|
|cmct3jp.dll|   cmct3ko.dll|   cmct3cht.dll|  mscc2chs.dll|
|mscc2jp.dll|   mscc2ko.dll|   mscc2cht.dll|  cmct3chs.dll|
|cmctljp.dll|   cmctlko.dll|   cmctlcht.dll|  cmctlchs.dll|
|cmdlgjp.dll|   cmdlgko.dll|   mscmccht.dll|  mscmcchs.dll|
|mscmcjp.dll|   mscmcko.dll|   cmdlgcht.dll|  cmdlgchs.dll|
|dbgrdjp.dll|   dbgrdko.dll|   dbgrdcht.dll|  dbgrdchs.dll|
|dblstjp.dll|   dblstko.dll|   dblstcht.dll|  dblstchs.dll|
|mcijp.dll|     mciko.dll|     mcicht.dll|    mcichs.dll|
|msadnjp.dll|   msadnko.dll|   msadncht.dll|  msadnchs.dll|
|adodcjp.dll|   adodcko.dll|   adodccht.dll|  adodcchs.dll|
|mschtjp.dll|   mschtko.dll|   mschtcht.dll|  mschtchs.dll|
|msch2jp.dll|   msch2ko.dll|   msch2cht.dll|  msch2chs.dll|
|mscomjp.dll|   mscomko.dll|   mscomcht.dll|  mscomchs.dll|
|datgdjp.dll|   datgdko.dll|   datgdcht.dll|  datgdchs.dll|
|datlsjp.dll|   datlsko.dll|   datlscht.dll|  datlschs.dll|
|datrpjp.dll|   datrpko.dll|   datrpcht.dll|  datrpchs.dll|
|dbrprjp.dll|   dbrprko.dll|   dbrprcht.dll|  dbrprchs.dll|
|flxgdjp.dll|   flxgdko.dll|   flxgdcht.dll|  flxgdchs.dll|
|mshfgjpn.dll|  mshfgkor.dll|  mshfgcht.dll|  mshfgchs.dll|
|htmprjp.dll|   htmprko.dll|   htmprcht.dll|  htmprchs.dll|
|inetjp.dll|    inetko.dll|    inetcht.dll|   inetchs.dll|
|msmpijp.dll|   msmpiko.dll|   msmpicht.dll|  msmpichs.dll|
|msmskjp.dll|   msmskko.dll|   msmskcht.dll|  msmskchs.dll|
|rdc20jp.dll|   rdc20ko.dll|   rdc20cht.dll|  rdc20chs.dll|
|rdo20jp.dll|   rdo20ko.dll|   rdo20cht.dll|  rdo20chs.dll|
|stdftjp.dll|   stdftko.dll|   stdftcht.dll|  stdftchs.dll|
|mswcrjp.dll|   mswcrko.dll|   mswcrcht.dll|  mswcrchs.dll|
|winskjp.dll|   winskko.dll|   winskcht.dll|  winskchs.dll|
|pcclpjp.dll|   pcclpko.dll|   pcclpcht.dll|  pcclpchs.dll|
|rchtxjp.dll|   rchtxko.dll|   rchtxcht.dll|  rchtxchs.dll|
|sysinjp.dll|   sysinko.dll|   sysincht.dll|  sysinchs.dll|
|tabctjp.dll|   tabctko.dll|   tabctcht.dll|  tabctchs.dll|

|ITA|FRA|ESP|DEU|
|---|---|---|---|
|mfc42ita.dll|  mfc42fra.dll|  mfc42esp.dll|  mfc42deu.dll|
|scrrnit.dll|   scrrnfr.dll|   scrrnes.dll|   scrrnde.dll|
|vb6it.dll|     vb6fr.dll|     vb6es.dll|     vb6de.dll|
|cmct2it.dll|   cmct2fr.dll|   cmct2es.dll|   cmct2de.dll|
|mscc2it.dll|   mscc2fr.dll|   mscc2es.dll|   mscc2de.dll|
|cmct3it.dll|   cmct3fr.dll|   cmct3es.dll|   cmct3de.dll|
|cmctlit.dll|   cmctlfr.dll|   cmctles.dll|   cmctlde.dll|
|mscmcit.dll|   mscmcfr.dll|   mscmces.dll|   mscmcde.dll|
|cmdlgit.dll|   cmdlgfr.dll|   cmdlges.dll|   cmdlgde.dll|
|dbgrdit.dll|   dbgrdfr.dll|   dbgrdes.dll|   dbgrdde.dll|
|dblstit.dll|   dblstfr.dll|   dblstes.dll|   dblstde.dll|
|mciit.dll|     mcifr.dll|     mcies.dll|     mcide.dll|
|msadnit.dll|   msadnfr.dll|   msadnes.dll|   msadnde.dll|
|adodcit.dll|   adodcfr.dll|   adodces.dll|   adodcde.dll|
|mschtit.dll|   mschtfr.dll|   mschtes.dll|   mschtde.dll|
|msch2it.dll|   msch2fr.dll|   msch2es.dll|   msch2de.dll|
|mscomit.dll|   mscomfr.dll|   mscomes.dll|   mscomde.dll|
|atgdit.dll|    datgdfr.dll|   datgdes.dll|   datgdde.dll|
|datlsit.dll|   datlsfr.dll|   datlses.dll|   datlsde.dll|
|datrpit.dll|   datrpfr.dll|   datrpes.dll|   datrpde.dll|
|dbrprit.dll|   dbrprfr.dll|   dbrpres.dll|   dbrprde.dll|
|flxgdit.dll|   flxgdfr.dll|   flxgdes.dll|   flxgdde.dll|
|mshfgit.dll|   mshfgfr.dll|   mshfges.dll|   mshfgde.dll|
|htmprit.dll|   htmprfr.dll|   htmpres.dll|   htmprde.dll|
|inetit.dll|    inetfr.dll|    inetes.dll|    inetde.dll|
|msmpiit.dll|   msmpifr.dll|   msmpies.dll|   msmpide.dll|
|msmskit.dll|   msmskfr.dll|   msmskes.dll|   msmskde.dll|
|rdc20it.dll|   rdc20fr.dll|   rdc20es.dll|   rdc20de.dll|
|rdo20it.dll|   rdo20fr.dll|   rdo20es.dll|   rdo20de.dll|
|stdftit.dll|   stdftfr.dll|   stdftes.dll|   stdftde.dll|
|mswcrit.dll|   mswcrfr.dll|   mswcres.dll|   mswcrde.dll|
|winskit.dll|   winskfr.dll|   winskes.dll|   winskde.dll|
|pcclpit.dll|   pcclpfr.dll|   pcclpes.dll|   pcclpde.dll|
|rchtxit.dll|   rchtxfr.dll|   rchtxes.dll|   rchtxde.dll|
|sysinit.dll|   sysinfr.dll|   sysines.dll|   sysinde.dll|
|tabctit.dll|   tabctfr.dll|   tabctes.dll|   tabctde.dll|

