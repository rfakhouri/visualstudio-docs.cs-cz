---
title: Instalace certifikátů vyžadovaných pro instalaci offline
description: Informace o instalaci certifikátů pro offline instalace sady Visual Studio.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 4ef5df077aabb02c9e9a4b46b0cfcbda76263b72
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58789338"
---
# <a name="install-certificates-required-for-visual-studio-offline-installation"></a>Instalace certifikátů vyžadovaných pro offline instalace sady Visual Studio

Visual Studio je primárně určený k instalaci na počítači připojené k Internetu, protože řada komponent jsou pravidelně aktualizovány. S několik kroků navíc, je však možné nasadit sady Visual Studio v prostředí, kde je funkční připojení k Internetu není k dispozici.

Instalační modul sady Visual Studio nainstaluje pouze obsah, který je důvěryhodný. Dělá to tak, že ověření podpisů Authenticode obsahu stahuje a ověřuje, že před instalací se považuje za důvěryhodný veškerý obsah. To udržuje vaše prostředí před útoky kde umístění stahování dojde k narušení. Visual Studio, které instalační program vyžaduje proto, že několik standardních Microsoft kořenové a zprostředkující certifikáty jsou nainstalovány a až do data na počítači uživatele. Pokud je počítač byl pravidelnou aktualizaci s Windows Update, podpisové certifikáty obvykle jsou aktuální. Pokud je počítač připojen k Internetu, během instalace sady Visual Studio může aktualizovat certifikáty podle potřeby k ověřování podpisů souborů. Pokud je počítač v režimu offline, certifikáty musí být aktualizován jiným způsobem.

## <a name="how-to-refresh-certificates-when-offline"></a>Jak obnovit certifikáty v režimu offline

Existují tři možnosti pro instalaci nebo aktualizaci certifikátů v režimu offline.

### <a name="option-1---manually-install-certificates-from-a-layout-folder"></a>Možnost 1 - Ruční instalace certifikátů ze složky rozložení

::: moniker range="vs-2017"

Při vytváření rozložení sítě potřebné certifikáty se stáhnou do složky certifikáty. Pak můžete ručně nainstalovat certifikáty poklepáním na každém ze souborů certifikátu a potom kliknutím na Průvodce správce certifikátů. Pokud budete vyzváni k zadání hesla, ponechte prázdné.

**Aktualizace**: Pro Visual Studio 2017 verze 15.8 ve verzi Preview 2 nebo novější, můžete ručně nainstalujte certifikáty pravým tlačítkem myši na každém ze souborů certifikátu, výběr instalace certifikátu a potom kliknutím na Průvodce správce certifikátů.

::: moniker-end

::: moniker range="vs-2019"

Při vytváření rozložení sítě potřebné certifikáty se stáhnou do složky certifikáty. Pravým tlačítkem myši na každém ze souborů certifikátu, výběr instalace certifikátu a potom kliknutím na Průvodce správce certifikátů můžete ručně nainstalovat certifikáty. Pokud budete vyzváni k zadání hesla, ponechte prázdné.

::: moniker-end

### <a name="option-2---distribute-trusted-root-certificates-in-an-enterprise-environment"></a>Možnost 2 - distribuci důvěryhodných kořenových certifikátů v podnikovém prostředí

Pro podniky s offline počítače, které nemají nejnovější kořenové certifikáty, Správce může pomocí pokynů na [konfigurovat Důvěryhodné kořeny a zakázané certifikáty](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11)) stránky je aktualizovat.

### <a name="option-3---install-certificates-as-part-of-a-scripted-deployment-of-visual-studio"></a>Možnost 3 – certifikáty nainstalovat jako součást skriptů nasazení sady Visual Studio

Pokud vytváříte skript nasazení sady Visual Studio v režimu offline klientským pracovním stanicím, můžete postupovat takto:

::: moniker range="vs-2017"

1. Kopírovat [nástroj Certificate Manager](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) ke sdílené složce instalace (například \\server\share\vs2017). Certmgr.exe není zahrnutý jako součást Windows, ale je k dispozici jako součást [sady Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

2. Vytvořte dávkový soubor pomocí následujících příkazů:

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

   **Aktualizace**: Pro Visual Studio 2017 verze 15,8 ve verzi Preview 2 nebo novější, vytvořte dávkový soubor pomocí následujících příkazů:

   ```cmd
   certmgr.exe -add [layout path]\certificates\manifestRootCertificate.cer -n "Microsoft Root Certificate Authority 2011" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\manifestCounterSignRootCertificate.cer -n "Microsoft Root Certificate Authority 2010" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\vs_installer_opc.RootCertificate.cer -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```
   
   Alternativně vytvořte dávkový soubor, který používá certutil.exe, která se dodává s Windows, pomocí následujících příkazů:
   
      ```cmd
   certutil.exe -addstore -f "Root" "[layout path]\certificates\manifestRootCertificate.cer

   certutil.exe -addstore -f "Root" [layout path]\certificates\manifestCounterSignRootCertificate.cer"

   certutil.exe -addstore -f "Root" "[layout path]\certificates\vs_installer_opc.RootCertificate.cer"
   ```

3. Dávkový soubor nasaďte do klienta. Tento příkaz musí spustit z procesu se zvýšenými oprávněními.

::: moniker-end

::: moniker range="vs-2019"

1. Kopírovat [nástroj Certificate Manager](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) ke sdílené složce instalace (například \\server\share\vs2019). Certmgr.exe není zahrnutý jako součást Windows, ale je k dispozici jako součást [sady Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

2. Vytvořte dávkový soubor pomocí následujících příkazů:

   ```cmd
   certmgr.exe -add [layout path]\certificates\manifestRootCertificate.cer -n "Microsoft Root Certificate Authority 2011" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\manifestCounterSignRootCertificate.cer -n "Microsoft Root Certificate Authority 2010" -s -r LocalMachine root

   certmgr.exe -add [layout path]\certificates\vs_installer_opc.RootCertificate.cer -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```
   
   Alternativně vytvořte dávkový soubor, který používá certutil.exe, která se dodává s Windows, pomocí následujících příkazů:
   
      ```cmd
   certutil.exe -addstore -f "Root" "[layout path]\certificates\manifestRootCertificate.cer

   certutil.exe -addstore -f "Root" [layout path]\certificates\manifestCounterSignRootCertificate.cer"

   certutil.exe -addstore -f "Root" "[layout path]\certificates\vs_installer_opc.RootCertificate.cer"
   ```

3. Dávkový soubor nasaďte do klienta. Tento příkaz musí spustit z procesu se zvýšenými oprávněními.

::: moniker-end

## <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>Co jsou certifikáty soubory ve složce pro certifikáty?

::: moniker range="vs-2017"

Tři. P12 soubory v této složce každý obsahují zprostředkující certifikát a kořenový certifikát. Většina systémů, které jsou aktuálně s aktualizací Windows mají tyto certifikáty už nainstalovaná.

* **ManifestSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **DPS 2011 pro podepisování kódu Microsoft**
        * Není nutné. Zlepšuje výkon v některých scénářích, pokud jsou k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2011**
        * Vyžaduje se v systémech Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace Windows.
* **ManifestCounterSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **Microsoft časové razítko DPS 2010**
        * Není nutné. Zlepšuje výkon v některých scénářích, pokud jsou k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2010**
        * Vyžaduje se pro systémy Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace Windows.
* **Vs_installer_opc. SignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **DPS pro podepisování kódu Microsoft**
        * Vyžaduje se pro všechny systémy. Všimněte si, že všechny aktualizace použije ze služby Windows Update v systémech nemusí obsahovat tento certifikát.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority**
        * Povinný parametr. Tento certifikát se dodává s systémy s operačním systémem Windows 7 nebo novější.

**Aktualizace**: Pro Visual Studio 2017 verze 15,8 ve verzi Preview 2 nebo novější, instalační program sady Visual Studio vyžaduje pouze kořenové certifikáty k instalaci v systému.

::: moniker-end

::: moniker range="vs-2019"

* **ManifestSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **DPS 2011 pro podepisování kódu Microsoft**
        * Není nutné. Zlepšuje výkon v některých scénářích, pokud jsou k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2011**
        * Vyžaduje se v systémech Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace Windows.
* **ManifestCounterSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **Microsoft časové razítko DPS 2010**
        * Není nutné. Zlepšuje výkon v některých scénářích, pokud jsou k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2010**
        * Vyžaduje se pro systémy Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace Windows.
* **Vs_installer_opc. SignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **DPS pro podepisování kódu Microsoft**
        * Vyžaduje se pro všechny systémy. Všimněte si, že všechny aktualizace použije ze služby Windows Update v systémech nemusí obsahovat tento certifikát.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority**
        * Povinný parametr. Tento certifikát se dodává s systémy s operačním systémem Windows 7 nebo novější.

Instalační program sady Visual Studio vyžaduje pouze kořenové certifikáty k instalaci v systému.

::: moniker-end

## <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>Proč jsou certifikáty vydané certifikáty složky nejsou nainstalovány automaticky?

Při podpisu je ověřený v online prostředí, rozhraní API pro Windows se používají ke stažení a přidejte certifikáty do systému. Během tohoto procesu dojde k ověření, že je certifikát důvěryhodný a povolené prostřednictvím Správce nastavení. Tento proces ověření nelze provést v prostředí nejvíce offline. Ruční instalace certifikátů umožňuje správcům zajistit certifikáty jsou důvěryhodné a splňují zásady zabezpečení organizace.

## <a name="checking-if-certificates-are-already-installed"></a>Kontroluje se, pokud jsou již nainstalovány certifikáty

Jedním ze způsobů můžete zkontrolovat na instalaci systému je postupujte podle těchto kroků:

1. Spustit **mmc.exe**.<br/>
  a. Klikněte na tlačítko **souboru**a pak vyberte **Přidat/odebrat modul Snap-in**.<br/>
  b. Dvakrát klikněte na panel **certifikáty**vyberte **účet počítače**a potom klikněte na tlačítko **Další**.<br/>
  c. Vyberte **místního počítače**, klikněte na tlačítko **Dokončit**a potom klikněte na tlačítko **OK**.<br/>
  d. Rozbalte **certifikáty (místní počítač)**.<br/>
  e. Rozbalte **důvěryhodných kořenových certifikačních autorit**a pak vyberte **certifikáty**.<br/>
    * Najdete v tomto seznamu nezbytné kořenové certifikáty.<br/>

   f. Rozbalte **zprostředkující certifikační autority**a pak vyberte **certifikáty**.<br/>
    * Najdete v tomto seznamu požadovaných zprostředkující certifikáty.<br/>

2. Klikněte na tlačítko **souboru**a pak vyberte **Přidat/odebrat modul Snap-in**.<br/>
  a. Dvakrát klikněte na panel **certifikáty**vyberte **Můj uživatelský účet**, klikněte na tlačítko **Dokončit**a potom klikněte na tlačítko **OK**.<br/>
  b. Rozbalte **certifikáty – aktuální uživatel**.<br/>
  c. Rozbalte **zprostředkující certifikační autority**a pak vyberte **certifikáty**.<br/>
    * Najdete v tomto seznamu požadovaných zprostředkující certifikáty.<br/>

Pokud nebyly v názvech certifikátů **vystaveno pro** sloupce, musí být nainstalovány.  Pokud zprostředkující certifikát byl pouze v **aktuálního uživatele** ukládat zprostředkující certifikát, pak je k dispozici pouze pro uživatele, který je přihlášen. Můžete potřebovat k instalaci pro ostatní uživatele.

## <a name="install-visual-studio"></a>Instalace sady Visual Studio

Po instalaci certifikátů nasazení sady Visual Studio můžete přejít pomocí pokynů z [nasazení z instalace v síti](create-a-network-installation-of-visual-studio.md#deploy-from-a-network-installation) část stránky "Vytvoření síťové instalace sady Visual Studio".

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
