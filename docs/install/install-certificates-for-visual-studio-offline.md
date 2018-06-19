---
title: Instalace certifikátů vyžadovaných pro instalaci offline sady Visual Studio | Microsoft Docs
description: Informace o instalaci certifikátů pro offline instalaci sady Visual Studio.
ms.date: 08/30/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70d6b30f3b264e5bdffc5f9c0f36ba17e67e8a5d
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
ms.locfileid: "31621165"
---
# <a name="install-certificates-required-for-visual-studio-offline-installation"></a>Instalace certifikátů vyžadovaných pro instalaci offline sady Visual Studio

Visual Studio je primárně určený k instalaci na počítači připojené k Internetu, protože celá řada komponent jsou pravidelně aktualizovány. S některými dalšími kroky, je však možné nasadit v prostředí Visual Studio, kde funkční připojení k Internetu je k dispozici.

Modul aplikace Visual Studio Instalační program nainstaluje pouze obsah, který je důvěryhodný. Dělá to pomocí ověření podpisů Authenticode obsahu stahování a ověřování, zda je důvěryhodný veškerý obsah před jeho instalací. Díky tomu prostředí před útoky kde dojde k ohrožení umístění stahování. Visual Studio, které instalační program proto vyžaduje instalaci několika standardní Microsoft kořenové a zprostředkující certifikáty a až do data v počítači uživatele. Pokud je počítač byl pravidelnou aktualizaci s Windows Update, podpisové certifikáty obvykle jsou aktuální. Pokud je počítač připojen k Internetu, během instalace sady Visual Studio může aktualizovat podle potřeby k ověřování podpisů souboru certifikáty. Pokud je počítač v režimu offline, certifikáty musí být aktualizován jiným způsobem.

## <a name="how-to-refresh-certificates-when-offline"></a>Jak aktualizovat certifikáty v režimu offline

Existují tři možnosti pro instalaci nebo aktualizaci certifikátů v režimu offline.

### <a name="option-1---manually-install-certificates-from-a-layout-folder"></a>Možnost 1 - certifikáty ručně instalovat ze složky rozložení

Při vytváření rozložení sítě potřebné certifikáty se stáhnou do složky certifikáty. Pak můžete ručně nainstalujte certifikáty dvakrát klikněte na každý ze souborů certifikátu a potom kliknutím na pomocí Průvodce správce certifikátů. Pokud se zobrazí výzva k zadání hesla, ponechte prázdné.

### <a name="option-2---distribute-trusted-root-certificates-in-an-enterprise-environment"></a>Možnost 2 - distribuci důvěryhodných kořenových certifikátů v podnikovém prostředí

Pro podniky s offline počítače, které nemají nejnovější kořenové certifikáty, Správce může pomocí pokynů na [konfigurovat Důvěryhodné kořeny a zakázané certifikáty](https://technet.microsoft.com/library/dn265983.aspx) stránky je aktualizovat.

### <a name="option-3---install-certificates-as-part-of-a-scripted-deployment-of-visual-studio"></a>Možnost 3 – Instalace certifikátů v rámci skriptované nasazení sady Visual Studio

Pokud vytváříte skript nasazení sady Visual Studio v režimu offline klientským pracovním stanicím, postupujte podle těchto kroků:

1. Kopírování [nástroj Certificate Manager](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) ke sdílené složce instalace (například \\server\share\vs2017). Certmgr.exe není zahrnutý jako součást Windows samostatně, ale je k dispozici jako součást [Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

2. Vytvořte dávkový soubor pomocí následujících příkazů:

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

3. Nasaďte dávkový soubor do klienta. Tento příkaz musí spustit z zvýšenými procesu.

## <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>Jaké jsou certifikáty soubory ve složce certifikáty?

Tři. P12 soubory v této složce každý obsahují zprostředkující certifikát a kořenový certifikát. Většina systémů, které jsou aktuální pomocí služby Windows Update mít tyto certifikáty již nainstalován.

* **ManifestSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **Microsoft kód podepisování PCA 2011**
        * Není požadováno. Zlepšuje výkon v některých scénářích, pokud je k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2011**
        * Vyžaduje v systémech Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace systému Windows.
* **ManifestCounterSignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **Microsoft časové razítko PCA 2010**
        * Není požadováno. Zlepšuje výkon v některých scénářích, pokud je k dispozici.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority 2010**
        * Vyžaduje se pro systémy Windows 7 Service Pack 1, které nemají nainstalované nejnovější aktualizace systému Windows.
* **Vs_installer_opc. SignCertificates.p12** obsahuje:
    * Zprostředkující certifikát: **PCA podepisování kódu Microsoft**
        * Vyžaduje se pro všechny systémy. Všimněte si, že systémy s všechny aktualizace ze služby Windows Update použít nemusí obsahovat tento certifikát.
    * Kořenový certifikát: **Microsoft kořenové certifikační autority**
        * Požadováno. Tento certifikát se dodává s systémy s operačním systémem Windows 7 nebo novější.

## <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>Proč jsou certifikáty ve složce Certifikáty není nainstalován automaticky?

Při ověření podpisu v online prostředí rozhraní API systému Windows slouží ke stažení a přidejte certifikáty do systému. Během tohoto procesu dojde k ověření, že je certifikát důvěryhodný a povolené prostřednictvím nastavení pro správu. Tento proces ověření nelze provést v prostředí nejvíce offline. Ruční instalace certifikátů umožňuje správcům zajistit certifikáty jsou důvěryhodné a splňují zásady zabezpečení své organizace.

## <a name="checking-if-certificates-are-already-installed"></a>Kontrola, pokud jsou již nainstalovány certifikáty

Jedním ze způsobů, zkontrolujte instalaci systému je postupujte podle těchto kroků:
1. Spustit **mmc.exe**.<br/>
  a. Klikněte na soubor a potom vyberte **přidat nebo odebrat modul Snap-in**.<br/>
  b. Klikněte dvakrát na **certifikáty**, vyberte **účet počítače**a potom klikněte na **Další**.<br/>
  c. Vyberte **místního počítače**, klikněte na tlačítko **Dokončit**a potom klikněte na **OK**.<br/>
  d. Rozbalte položku **certifikáty (místní počítač)**.<br/>
  e. Rozbalte položku **důvěryhodné kořenové certifikační autority**a potom vyberte **certifikáty**.<br/>
    * Zkontrolujte seznam nezbytné kořenové certifikáty.<br/>

   f. Rozbalte položku **zprostředkující certifikační autority**a potom vyberte **certifikáty**.<br/>
    * Zkontrolujte seznam požadované zprostředkující certifikáty.<br/>

2. Klikněte na soubor a vyberte **přidat nebo odebrat modul Snap-in**.<br/>
  a. Klikněte dvakrát na **certifikáty**, vyberte **uživatelským účtem**, klikněte na tlačítko **Dokončit**a potom klikněte na **OK**.<br/>
  b. Rozbalte položku **certifikáty – aktuální uživatel**.<br/>
  c. Rozbalte položku **zprostředkující certifikační autority**a potom vyberte **certifikáty**.<br/>
    * Zkontrolujte seznam požadované zprostředkující certifikáty.<br/>

Pokud nebyly v názvech certifikátů **vystaveno pro** sloupců, musí být nainstalován.  Pokud certifikát zprostředkující byla jenom v **aktuální uživatel** zprostředkující certifikát úložiště, pak je k dispozici pouze uživateli, který je přihlášen. Možná budete muset nainstalovat pro ostatní uživatele.

## <a name="install-visual-studio"></a>Instalaci sady Visual Studio

Po instalaci certifikátů, nasazení sady Visual Studio můžete pokračovat podle pokynů z [nasazení z síťovou instalaci](create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation) části stránky "Vytvořit síťovou instalaci sady Visual Studio".

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
