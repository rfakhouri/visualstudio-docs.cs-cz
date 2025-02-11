---
title: Vzdálené ladění projektu ve Visual C++ | Dokumentace Microsoftu
ms.custom: remotedebugging
ms.date: 08/14/2018
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
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: fbfdb246769ac55afd7f164d91673e39e293f4c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62903500"
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>Vzdálené ladění projektu ve Visual C++ v sadě Visual Studio
Ladění aplikace Visual Studio na jiném počítači, nainstalovat a spustit nástroje remote tools v počítači, kde bude nasazovat aplikace, nakonfigurujte projekt tak, aby připojení ke vzdálenému počítači ze sady Visual Studio a pak nasaďte a spusťte aplikaci.

![Vzdálený ladicí program komponenty](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

Informace o vzdáleném ladění aplikací pro univerzální aplikace Windows (UPW) najdete v tématu [ladit nainstalovaný balíček aplikace](debug-installed-app-package.md).

## <a name="requirements"></a>Požadavky

Vzdálený ladicí program podporuje se ve Windows 7 a novější (ne telefon) a verze systému Windows Server od verze Windows Server 2008 Service Pack 2. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Ladění mezi dvěma počítači připojený prostřednictvím proxy serveru není podporováno. Ladění přes vysokou latencí nebo připojení s malou šířkou pásma, jako je například telefonického Internetu, nebo přes Internet napříč zeměmi se nedoporučuje a může selhat nebo být příliš pomalé.

## <a name="download-and-install-the-remote-tools"></a>Stáhněte a nainstalujte nástroje remote tools

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> V některých případech může být nejúčinnější pro spuštění vzdáleného ladicího programu ze sdílené složky. Další informace najdete v tématu [spuštění vzdáleného ladicího programu ze sdílené složky](../debugger/remote-debugging.md#fileshare_msvsmon).

## <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro další uživatele, změnit režim ověřování, nebo číslo portu pro vzdálené ladění, naleznete v tématu [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

## <a name="remote_cplusplus"></a> Vzdálené ladění projektu Visual C++
 V následujícím postupu, název a cestu k projektu je C:\remotetemp\MyMfc a je název vzdáleného počítače **MJO DL**.

1. Vytvoření aplikace knihovny MFC s názvem **mymfc.**

2. Nastavit zarážku někde v aplikaci, která je snadno dosaženo, například v **MainFrm.cpp**, na začátku `CMainFrame::OnCreate`.

3. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a vyberte **vlastnosti**. Otevřít **ladění** kartu.

4. Nastavte **ladicí program ke spuštění** k **vzdálený ladicí program Windows**.

    ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")

5. Proveďte změny následujících vlastností:

   |Nastavení|Hodnota|
   |-|-|
   |Vzdálený příkaz|C:\remotetemp\mymfc.exe|
   |Pracovní adresář|C:\remotetemp|
   |Název vzdáleného serveru|MJO DL:*číslo_portu*|
   |Připojení|Vzdálený s ověřováním Windows|
   |Typ ladicího programu|Pouze nativní|
   |Adresář nasazení|C:\remotetemp.|
   |Další soubory k nasazení|C:\data\mymfcdata.txt.|

    Pokud nasadíte další soubory (volitelné), složka musí existovat v obou počítačích.

6. V Průzkumníku řešení klikněte pravým tlačítkem na řešení a zvolte **nástroje Configuration Manager**.

7. Pro **ladění** konfigurace, vyberte **nasadit** zaškrtávací políčko.

    ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")

8. Spustit ladění (**ladit > Spustit ladění**, nebo **F5**).

9. Spustitelný soubor je automaticky nasadí do vzdáleného počítače.

10. Pokud se zobrazí výzva, zadejte přihlašovací údaje k síti pro připojení ke vzdálenému počítači.

     Požadované přihlašovací údaje jsou specifické pro konfiguraci zabezpečení vaší sítě. Například v počítači domény, může vybrat si certifikát zabezpečení nebo zadejte název domény a heslo. Na počítači mimo doménu, můžete například zadat název počítače a platné uživatelské jméno účtu, jako je třeba <strong>MJO-DL\name@something.com</strong>, spolu s správné heslo.

11. V počítači, Visual Studio měli byste vidět zastavením spuštění na zarážce.

    > [!TIP]
    > Alternativně můžete nasadit soubory jako samostatný krok. V **Průzkumníku řešení klikněte** klikněte pravým tlačítkem myši **mymfc** uzel a klikněte na tlačítko **nasadit**.

    Pokud máte souborům bez kódu, které jsou vyžadované aplikací, můžete je zadat **další soubory k nasazení** na **vzdálený ladicí program Windows** stránky.

    Alternativně můžete zahrnout soubory ve vašem projektu a nastavit **obsahu** vlastnost **Ano** v **vlastnosti** stránky pro každý soubor. Tyto soubory se zkopírují do **adresáře nasazení** zadané **vzdálený ladicí program Windows** stránky. Můžete také změnit **typ položky** k **kopírovat soubor** a zadat další vlastnosti existuje, pokud potřebujete soubory zkopírovány do podsložky **adresáře nasazení**.

## <a name="set-up-debugging-with-remote-symbols"></a>Nastavení se vzdálený symboly ladění

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>Viz také
- [Ladění v sadě Visual Studio](../debugger/index.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
- [Konfigurace brány firewall ve Windows pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)
- [Vzdálené ladění ASP.NET na vzdáleném počítači se službou IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)