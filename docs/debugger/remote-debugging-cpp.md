---
title: Vzdálené ladění projektu Visual C++ | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: df0caacf8d3d99117208ce197e075f20f6df8b5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>Vzdálené ladění projektu Visual C++ v sadě Visual Studio
K ladění aplikace z Visual Studia na jiném počítači, instalaci a spuštění nástrojů pro vzdálenou na počítači, kde budou nasazovat aplikace, nakonfigurujete svůj projekt k připojení ke vzdálenému počítači ze sady Visual Studio, nasazení a spuštění aplikace.

![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

Informace o vzdálené ladění univerzální aplikace pro Windows (UWP) najdete v tématu [ladění balíčku aplikace nainstalována](debug-installed-app-package.md).

## <a name="requirements"></a>Požadavky

Vzdáleného ladicího programu je podporována v systému Windows 7 nebo novější (není phone) a verzí systému Windows Server, počínaje systémem Windows Server 2008 Service Pack 2. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Mezi dvěma počítači připojené prostřednictvím proxy serveru se nepodporuje ladění. Ladění nad vysokou latencí nebo připojení s malou šířkou pásma, jako je například telefonického Internetu, nebo přes Internet napříč zemích se nedoporučuje a může selhat nebo být příliš pomalé.
  
## <a name="download-and-install-the-remote-tools"></a>Stáhněte a nainstalujte nástroje pro vzdálenou

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
> [!TIP]
> V některých případech může být nejúčinnější ke spuštění vzdáleného ladicího programu ze sdílené složky. Další informace najdete v tématu [spuštění vzdáleného ladicího programu ze sdílené složky](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

## <a name="remote_cplusplus"></a> Vzdálené ladění projektu Visual C++  
 V následujícím postupu, název a cesta k projektu je C:\remotetemp\MyMfc a je název vzdáleného počítače **MJO DL**.  
  
1.  Vytvoření aplikace knihovny MFC s názvem **mymfc.**  
  
2.  Nastavit zarážky někde v aplikaci, která je snadno dosaženo, například v **MainFrm.cpp**, na začátku `CMainFrame::OnCreate`.  
  
3.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt a vyberte **vlastnosti**. Otevřete **ladění** kartě.  
  
4.  Nastavte **ladicí program ke spuštění** k **vzdáleného ladicího programu Windows**.  
  
     ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")  
  
5.  Proveďte následující změny na vlastnosti:  
  
    |Nastavení|Hodnota|
    |-|-|  
    |Vzdálený příkaz|C:\remotetemp\mymfc.exe|  
    |Pracovní adresář|C:\remotetemp|  
    |Název vzdáleného serveru|MJO-DL:*číslo_portu*|  
    |Připojení|Vzdálené pomocí ověřování systému Windows|  
    |Typ ladicí program|Jenom Native|  
    |Adresáře nasazení|C:\remotetemp.|  
    |Další soubory pro nasazení|C:\data\mymfcdata.txt.|  
  
     Pokud nasadíte další soubory (volitelné), složka musí existovat na obou počítačích.  
  
6.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení a zvolte **nástroje Configuration Manager**.  
  
7.  Pro **ladění** konfiguraci, vyberte **nasadit** zaškrtávací políčko.  
  
     ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")  
  
8.  Spuštění ladění (**ladění > Spustit ladění**, nebo **F5**).  
  
9. Spustitelný soubor je automaticky nasadí do vzdáleného počítače.  
  
10. Pokud se zobrazí výzva, zadejte přihlašovací údaje k síti pro připojení ke vzdálenému počítači.  
  
     Požadovaná pověření jsou specifické pro konfigurace zabezpečení sítě. Například v počítači domény, může vybrat si certifikát zabezpečení nebo zadejte název domény a heslo. Na počítači nepřipojená k doméně, můžete zadat název počítače a platné uživatelské jméno účtu, jako je třeba **MJO-DL\name@something.com**, společně s správné heslo.  
  
11. V počítači, Visual Studio byste měli vidět, že je zastavená provádění u zarážky.  
  
    > [!TIP]
    >  Alternativně můžete nasadit soubory jako samostatný krok. V **Průzkumníku řešení** klikněte pravým tlačítkem myši **mymfc** uzel a potom zvolte **nasadit**.  
  
 Pokud máte jiný kód soubory, které je potřeba použít v aplikaci, musíte zahrnout je do projektu Visual Studia. Vytvořte složku projekt pro další soubory (v **Průzkumníku řešení**, klikněte na tlačítko **Přidat > novou složku**.) Pak přidat soubory do složky (v **Průzkumníku řešení**, klikněte na tlačítko **Přidat > existující položka**, vyberte soubory). Na **vlastnosti** stránky pro každý soubor, nastavte **kopírovat do výstupního adresáře** k **vždy Kopírovat**.
  
## <a name="set-up-debugging-with-remote-symbols"></a>Nastavení ladění se vzdálené symboly 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)] 
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)   
 [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)   
 [Vzdálené ladění technologie ASP.NET v počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)