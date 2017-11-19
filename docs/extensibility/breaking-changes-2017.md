---
title: "Nejnovější změny ve Visual Studio 2017 rozšiřitelnost | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d474374a0c7603bc9b6995783bbed96c81c8907
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Změny v rozšíření Visual Studio 2017

S Visual Studio 2017 jsme nabídky [rychlejší, světlejšího váhy instalace produktu Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer) který snižuje dopad sady Visual Studio v systémech uživatelů, zároveň dává uživatelům větší volba přes úlohy a funkce které se nainstalují. Pro podporu těchto vylepšení, jsme udělali změny model rozšiřitelnosti a provedli některé dodatečné změny rozšíření sady Visual Studio. Tento dokument popisuje technické informace o těchto změnách a co můžete udělat je řešit. Upozorňujeme, že určité informace se podrobnosti implementace bodu v čase a dají změnit později.

## <a name="changes-affecting-vsix-format-and-installation"></a>Změny, které mají vliv na formát VSIX a instalace

Jsme se představení VSIX v3 formátu (verze 3) pro podporu šedé – instalace produktu.

Mezi změny ve formátu VSIX patří:

* Prohlášení o požadovaných součástí instalace. K poskytování na potenciálu lightweight, fast instalace sady Visual Studio, instalační program teď nabízí další možnosti konfigurace pro uživatele. V důsledku toho zajistit, že se nainstalují funkce a součásti požadované nástrojem rozšíření, bude nutné rozšíření deklarovat závislé.
  * Instalační program Visual Studio 2017 bude automaticky nabízet získat a nainstalovat komponenty potřebné pro uživatele v rámci instalace rozšíření.
  * Také se upozornění uživatelů při pokusu o instalaci rozšíření, které nebyl vytvořen pomocí nový formát v3 VSIX i v případě, že byla označena jako cílení na verzi 15.0 jejich manifestu.
* Rozšířené možnosti pro formát VSIX. K poskytování na [nízká dopad instalace](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install) sady Visual Studio, který taky podporuje nainstaluje vedle sebe, jsme už uložení většina konfiguračních dat do registru systému a byl přesunut Visual Studio konkrétní sestavení z mezipaměti GAC. Můžeme také vyšší funkce VSIX formátu a VSIX instalace modulu, umožňuje použít ji spíš než MSI nebo EXE instalace rozšíření pro některé typy instalace.

  Nové funkce, které patří:

  * Registrace do zadané instance Visual Studio.
  * Instalace mimo [složky rozšíření](set-install-root.md).
  * Zjišťování na architektuře procesoru.
  * Závislost na jazyk oddělené jazykových sad.
  * Instalace s [NGEN podporu](ngen-support.md).

## <a name="building-an-extension-for-visual-studio-2017"></a>Vytváření rozšíření pro Visual Studio 2017

Návrhář nástrojů pro vytváření nového VSIX v3 manifestu formát je teď dostupná v Visual Studio 2017. Naleznete v doprovodné dokumentu [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) podrobnosti o použití návrháře nástrojů nebo vytváření ruční aktualizace do projektu a manifest vyvíjet rozšíření VSIX v3.

## <a name="change-visual-studio-user-data-path"></a>Změn: Cesta k datům uživatele sady Visual Studio

Na každém počítači může být dříve, pouze jedna instalace jednotlivých hlavní verze sady Visual Studio. Pro podporu instalace Visual Studio 2017 vedle sebe, může existovat více cesty k datům uživatele pro sadu Visual Studio v počítači uživatele.

Kód spuštění v rámci procesu Visual Studio je třeba aktualizovat použití nastavení správce Visual Studio. Kód spuštěný mimo proces sady Visual Studio můžete najít uživatele cestu konkrétní instalaci sady Visual Studio [podle pokynů tady](locating-visual-studio.md).

## <a name="change-global-assembly-cache-gac"></a>Změna: Globální mezipaměti sestavení (GAC)

Většina základních sestavení sady Visual Studio jsou již nainstalovány do mezipaměti GAC. Byly provedeny následující změny, aby kód spuštěný v sadě Visual Studio procesu stále najít požadované sestavení za běhu.

> [!NOTE]
> [INSTALLDIR] níže odkazuje na kořenový adresář instalace sady Visual Studio. VSIXInstaller.exe bude automaticky naplnit to, ale chcete napsat kód vlastní nasazení, přečtěte si [vyhledání sady Visual Studio](locating-visual-studio.md).

* Sestavení, které byly nainstalovány pouze do mezipaměti GAC:
  * Tyto sestavení jsou teď nainstalované v části [INSTALLDIR] \Common7\IDE\, [INSTALLDIR] \Common7\IDE\PublicAssemblies nebo \Common7\IDE\PrivateAssemblies [INSTALLDIR]. Tyto složky jsou součástí sady Visual Studio procesu testování cesty.
* Sestavení, které byly nainstalovány do cesty jiný zjišťování a do mezipaměti GAC:
  * Kopie v mezipaměti GAC byla odebrána z instalačního programu.
  * Soubor .pkgdef byl přidán k určení základní položku kódu pro sestavení.

    Příklad:
    
    ```xml
    [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
    "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
    "publicKeyToken"="Public Key Token"
    "culture"="neutral"
    "version"=15.0.0.0
    ```
    V době běhu subsystém pkgdef Visual Studio bude sloučit tyto položky do procesu Visual Studio runtime konfigurační soubor (v části [VSAPPDATA]\devenv.exe.config) jako [ `<codeBase>` ](https://msdn.microsoft.com/en-us/library/efs781xb(v=vs.110).aspx) elementy. Toto je doporučený způsob umožníte proces sady Visual Studio najít sestavení, protože při ní nedochází hledání prostřednictvím zjišťování cesty.

### <a name="reacting-to-this-breaking-change"></a>Nereagují v rámci této narušující změně.

* Pokud toto rozšíření je spuštěna v rámci procesu Visual Studio:
  * Váš kód bude moci najít základních sestavení sady Visual Studio.
  * Zvažte použití souboru .pkgdef Pokud chcete zadat cestu k vaší sestavení v případě potřeby.
* Pokud toto rozšíření je spuštěn mimo proces sady Visual Studio:
  * Vezměte v úvahu hledá základních sestavení sady Visual Studio v části [INSTALLDIR] \Common7\IDE\, [INSTALLDIR] \Common7\IDE\PublicAssemblies nebo \Common7\IDE\PrivateAssemblies [INSTALLDIR] pomocí překladače konfigurační soubor nebo sestavení.

## <a name="change-reduce-registry-impact"></a>Změna: Snížit dopad registru

### <a name="global-com-registration"></a>Globální registrace modelu COM

* Dříve Visual Studio nainstalované mnoho klíče registru do podregistrů HKEY_CLASSES_ROOT a HKEY_LOCAL_MACHINE pro podporu nativních registrace COM. Pokud chcete odstranit tento dopad, Visual Studio teď používá [Bezregistrační aktivace pro komponenty modelu COM](https://msdn.microsoft.com/en-us/library/ms973913.aspx).
* V důsledku toho většina TLB / OLB / knihovny DLL v části % ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv již nejsou nainstalovány ve výchozím nastavení Visual Studio. Tyto soubory jsou nyní nainstalovat pod [INSTALLDIR] s odpovídající COM bez registrace manifesty používá proces hostitele Visual Studio.
* Externí kód, který využívá globální registraci Visual Studio COM – rozhraní modelu COM v důsledku toho již najdete tyto registrace. Kód spuštění v rámci procesu Visual Studio se nezobrazí rozdíl.

### <a name="visual-studio-registry"></a>Visual Studio registru

* Dřív nainstalované sady Visual Studio do systému HKEY_LOCAL_MACHINE a HKEY_CURRENT_USER podregistrů pod klíčem Visual Studio specifické pro mnoho klíče registru:
  * HKLM\Software\Microsoft\VisualStudio\\**verze**: klíče registru vytvořené MSI instalační programy a rozšíření na počítač.
  * HKCU\Software\Microsoft\VisualStudio\\**verze**: klíče registru vytvořené pomocí sady Visual Studio ukládat specifická nastavení uživatele.
  * HKCU\Software\Microsoft\VisualStudio\\**verze**_Config: kopie Visual Studio HKLM klíč výše uvedených plus klíče registru sloučit z .pkgdef souborů tak, že rozšíření.
* Pro snížení vlivu na registru, Visual Studio teď používá [RegLoadAppKey](https://msdn.microsoft.com/en-us/library/windows/desktop/ms724886(v=vs.85).aspx) funkce pro ukládání klíčů registru v privátní binárního souboru pod [VSAPPDATA]\privateregistry.bin. Velmi malý počet Visual Studio zkratky specifické pro zůstat v registru systému.
* Existující kód běžících v rámci procesu Visual Studio není ovlivněná. Visual Studio přesměruje všechny operace registru pod klíčem HKCU Visual Studio konkrétní privátní registru. Čtení a zápis do jiných umístění registru bude nadále používat systémový registr.
* Externí kód bude muset načíst a čtení z tohoto souboru pro Visual Studio položky registru.

### <a name="reacting-to-this-breaking-change"></a>Nereagují v rámci této narušující změně.

* Externí kódu mají být převedeny na použití Bezregistrační aktivace pro komponenty modelu COM také.
* Externí součásti můžete vyhledat umístění sady Visual Studio [podle pokynů tady](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup).
* Doporučujeme použít externí součásti [externí správce nastavení](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.settings.externalsettingsmanager.aspx) místo čtení/zápis přímo k sadě Visual Studio klíče registru.
* Zkontrolujte, zda součásti, které používá rozšíření může implementovat jiný postup pro registraci. Rozšíření ladicí program může být například moct využívat nové [msvsmon registrace COM souboru JSON](migrate-debugger-COM-registration.md).
