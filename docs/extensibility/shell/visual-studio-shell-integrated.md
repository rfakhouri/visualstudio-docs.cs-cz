---
title: "Prostředí Visual Studio (integrovaný) | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, integrated mode features
- Shell [Visual Studio], integrated mode features
ms.assetid: 0b40d495-f17f-4bb9-ace8-b365a7172784
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f2159e0be2f54929e28a45215588515a522b542e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-shell-integrated"></a>Prostředí Visual Studio (integrovaný)
Prostředí sady Visual Studio integrované zahrnuje integrované vývojové prostředí (IDE), integrace ovládacích prvků zdrojového a ladicí program. Žádný programovací jazyk je zahrnuta. Integrované prostředí však poskytuje rozhraní, které umožňuje přidat programovací jazyky.  
  
 Prostředí sady Visual Studio integrované je ve skutečnosti kombinací prostředí sady Visual Studio izolované plus další instalace, které zahrnují integrované prostředí konkrétní součásti.  Aplikace integrované prostředí by měl obsahovat obě izolované prostředí redistribuovatelného balíčku z [redistribuovatelný balíček Microsoft Visual Studio Shell (Izolovaná)](http://go.microsoft.com/fwlink/?LinkId=616022) a také redistribuovatelného balíčku integrované prostředí z [sady Microsoft Visual Studio Shell (integrovaný) Redistributable Package](http://go.microsoft.com/fwlink/?LinkId=616021).  
  
> [!NOTE]
>  Než se dostanete k Distribuovatelné balíčky izolované a integrované prostředí, vyzve k vyplnění přehled stručný zákazníků.  Po vyplnění průzkumu, budete přesměrováni na stránku s odkazy na stažení redistribuovatelný balíček Visual Studio připojení.  Můžete najít odkazy stažení při dalších návštěvách k webu Visual Studio připojení v části **programy &#124; PROSTŘEDÍ VISUAL STUDIO 2015 integrované a IZOLOVANÉ** kartě.  
  
 Při instalaci aplikace integrované prostředí na stejném počítači jako s plnou verzí sady Visual Studio, budete součásti vaší aplikace integrovat přímo do sady Visual Studio.  
  
## <a name="features-in-the-integrated-shell"></a>Funkce integrované prostředí  
  
|||  
|-|-|  
|Oblast funkcí|Funkce|  
|Jazyková podpora|-None|  
|IDE – integrované vývojové prostředí|<ul><li>Nastavení<br /><br /> <ul><li>Vytvoření nastavení</li><li>Import a export nastavení</li><li>Resetovat nastavení</li></ul></li><li>**Sada nástrojů** integrace</li><li>**Seznam úkolů** integrace</li><li>Integrace nápovědy</li><li>**Možnosti** dialogové okno</li><li>Písma a barev správy</li><li>**Výstup** okna</li><li>**Příkaz** okna</li><li>Správa oken</li><li>Příkazy nabídky a vazeb klíče</li><li>Modul runtime jazyka domény (DSL)</li></ul>|  
|Systém projektu a typů projektu|-Řešení a řešení složek<br />-Řešení nástroje configuration manager<br />-Položek správy<br />-Řešení jednoprojektové a vícenásobného projektu<br />-Application Designer (vlastnosti zjednodušené projektu)<br />-Přidat webový odkaz<br />-Přidat odkaz na službu<br />Jednoprojektové<br />– Typy projektů webové stránky<br />-Projekty webových aplikací|  
|Sestavení|-Vlastní kroky sestavení v integrovaném vývojovém prostředí<br />-Předkompilaci pro ochranu duševního vlastnictví (IP)<br />-Podepisování kódu<br />     MSBuild|  
|Editor|-Kód procházení nástroje (jednotné najít, definice zdroje, dědičnost)<br />– Navigace kód<br />-IntelliSense<br />-Inteligentní značky<br />-Refaktoring<br />-Velmi výpis<br />-Filtrování IntelliSense<br />-   **Code Definition** okna|  
|Návrhář|– Návrhář Windows Presentation Foundation<br />-Návrhář formulářů Windows<br />-Webové Designer a HTML Editor|  
|Data|-   **V Průzkumníku serveru** (zjednodušená: pouze data). Viz poznámka 1.<br />-   **Zdroje dat** okna<br />-Úplnou sadu dat ovládacích prvků<br />– Editor XML<br />-Data vytvořit vazbu na místní zdroj dat (. MDF nebo. MDB)<br />-Data bind objektu<br />-Data bind k webové službě<br />-Data vytvořit vazbu k místní databázi serveru<br />-Data vytvořit vazbu na vzdálený databázový server<br />-DDL nástroje pro vzdálená data<br />-   **V Průzkumníku serveru** rozšiřitelnost ([!INCLUDE[vsipsdk](../includes/vsipsdk_md.md)] ukázky)|  
|Ladicí program|– Místní ladění. Další informace v poznámce 2.<br />-Spravované ladění<br />– Místní ladění<br />-Připojení k místní proces<br />-Přiřadit vzdáleného procesu<br />-Anonymní delegáta<br />-Aplikační domény<br />– ASPX ladění<br />– Atributy<br />-Break během zkušební verze Func<br />-Zarážky<br />-Omezení zarážek<br />-Zásobník volání<br />-   **Příkaz** okna<br />-Ladění mezi vlákny<br />-Datových tipech<br />– Dat vizualizér<br />– Ladicí program podpora pro Pomocníci spravovaného ladění (mda)<br />– Ladicí program podpora pro předávání typů<br />-Podpora DTEEvents OTB<br />-SVK krokovač<br />-Ladicí program AppID testu (DBGCLR)<br />-Profil ladicí program<br />-Ladicího programu nástrojů a možností<br />-Ladění iterátorů<br />-Vyhodnocení výrazu návrhu<br />-Vyhodnocovací filtr výrazů C#<br />-Zpětný překlad<br />-Upravit a pokračovat<br />– Windows vyhodnocování výraz (sledovat, místní hodnoty, automobily)<br />– Pomocníka výjimka<br />– Výjimky<br />-Provádění<br />– Obecné typy<br />-Získávání správné zdroje<br />-Ladění/clusteru HPC<br />-Integrated ladění více jazyků<br />-Spolupráce ladění<br />-V běhu ladění<br />– Místní ladění<br />-Spravované ladění<br />-Ruční kontrola (procesy okna)<br />-Paměti<br />-Podpora minimální výpis<br />-Moduly<br />-Více procesů ladění<br />-Nativní ladění<br />-Nový modul podpora ladění<br />-Ladění optimalizovaný kód<br />-Windows output filtrování<br />-Zpracování hostování pro spravované ladění<br />-Procesy<br />-Quickwatch<br />-Registry<br />-Zaregistruje v zásobníku<br />-Vzdálené ladění<br />-Návratové hodnoty<br />-Ladění skriptu<br />-Source služby podpory<br />-Zabezpečení<br />–--Vedle sebe<br />-SQL<br />– Server symbol<br />-Trasování body<br />-Přístup z více vláken<br />-Vizualizace<br />-Ladicí program extensible šablony stylů transformace XSLT (Language)|  
|Podpora 64bitových technologií|-64-bit ladění pro spravovaná a nativní kód, všechny jazyky<br />-x64 nativní podporu|  
|Správa zdrojového kódu (SCC)|-Základní SCC integrace. Viz poznámka 3.<br />-Nástroje a možnosti ověření|  
|Rozšiřitelnost|-Využívat VSPackages a MEF komponenty|  
  
## <a name="notes"></a>Poznámky  
  
#### <a name="1-data-tools"></a>1. Datové nástroje  
 Integrované prostředí zahrnuje databáze vývojovými nástroji, např. podpora rozšiřitelnost dat a zjednodušeného **Průzkumníku řešení**. Však systém SQL Server Express, SQL Reporting a Crystal Reports nejsou zahrnuty v integrované prostředí.  
  
#### <a name="2-debugging-support"></a>2. Podpora ladění  
 Integrované prostředí obsahuje stejný ladění modul, který je součástí komunity verze sady Visual Studio. Modul ladění zahrnuje běžné ladicí program pro spravovaný kód a souvisejících funkcí, například spuštění, Attach, nastavit bod přerušení, upravit a pokračovat a ostatní. Modul ladění ale nepodporuje ladění databáze systému SQL Server.  
  
 I když se podpora pro nativní ladění je zahrnutý v balíčku základní ladicí program, není možné jej tak, aby podporoval další rozšířit.  
  
#### <a name="3-source-code-control-integration"></a>3. Integrace ovládacích prvků zdrojového kódu  
 K implementaci řízení zdrojového kódu (SCC) a pro poskytování řízení na základě MSSCCI běžné zdroje součásti pro integraci, poskytuje integrované prostředí rozhraní API.  
  
 I když SCC integrace není regulární funkce Pro edice Visual Studia, SCC integrace je součástí integrované prostředí.  
  
#### <a name="4-build-support"></a>4. Podpora sestavení  
 Integrované prostředí poskytuje podporu sestavení. Informace o sestavení v najdete [MSBuild – Reference](../../msbuild/msbuild-reference.md).  
  
## <a name="features-not-included-in-the-integrated-shell"></a>Funkce, které nejsou součástí integrované prostředí  
 Následuje seznam funkcí, které nejsou součástí integrované prostředí:  
  
-   Návrhář tříd  
  
-   [Preemptivní ochrana – Dotfuscatoru](../../ide/dotfuscator/index.md)  
  
-   Jazykové funkce  
  
-   VSHost  
  
-   Žádné jazyky Visual Studio nebo jejich přidružené projektu šablony nebo šablony položek projektu, jsou součástí integrované prostředí. Žádná konkrétní jazyk implementace dalších funkcí jsou zahrnuté pro fragmentů kódu jazyka Visual Basic.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio SDK](../visual-studio-sdk.md)