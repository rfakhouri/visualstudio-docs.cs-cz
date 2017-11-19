---
title: "Vzdálené ladění jazyka C# nebo projektu jazyka Visual Basic v sadě Visual Studio | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords: remote debugging, setup
ms.assetid: a9753fbb-e7f4-47f0-9dbe-9de90c6c8457
caps.latest.revision: "65"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5bfa2e09d96f383b39eb392d5172cf38d750cef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="remote-debugging-a-c-or-visual-basic-project-in-visual-studio"></a>Vzdálené ladění projektu C# nebo Visual Basic v sadě Visual Studio
K ladění aplikace z Visual Studia, která byla nasazena do jiného počítače, instalaci a spuštění nástrojů pro vzdálenou na počítači, kde jste nasadili aplikace, nakonfigurujete svůj projekt pro připojení ke vzdálenému počítači ze sady Visual Studio a pak spusťte aplikaci.

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
  
## <a name="BKMK_setup"></a>Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).
  
## <a name="remote_csharp"></a>Vzdálené ladění projektu
Ladicí program nemůže nasadit Visual C# nebo Visual Basic aplikací klasické pracovní plochy ke vzdálenému počítači, ale stále je může vzdáleně následujícím způsobem ladění. Následující postup předpokládá, že chcete ladění na počítači s názvem **MJO DL**, jak je znázorněno na obrázku níže.
  
1.  Vytvoření projektu WPF s názvem **MyWpf**.  
  
2.  Nastavte zarážky někde v kódu, který je snadno dostupný.  
  
     Například může nastavit zarážky v rutině tlačítka. K tomuto účelu MainWindow.xaml, otevřít, přidání ovládacího prvku tlačítko z panelu nástrojů a pak dvakrát klikněte na tlačítko otevřete její obslužná rutina.
  
3.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **vlastnosti**.  
  
4.  Na **vlastnosti** vyberte **ladění** kartě.  
  
     ![RemoteDebuggerCSharp](../debugger/media/remotedebuggercsharp.png "RemoteDebuggerCSharp")  
  
5.  Zajistěte, aby **pracovní adresář** textové pole je prázdné.  
  
6.  Zvolte **použít vzdálený počítač**a typ **MJO-DL:4022** v textovém poli. (zobrazený v okně vzdáleného ladicího programu číslo portu je 4022. Číslo portu zvýší 2 v jednotlivých verzí sady Visual Studio).
  
7.  Ujistěte se, že **povolit ladění nativního kódu** není vybraná.  
  
8.  Sestavte projekt.  
  
9. Vytvořte složku na vzdáleném počítači, který je cesta ke stejné jako **ladění** složky v počítači Visual Studio:  **\<zdrojová cesta > \MyWPF\MyWPF\bin\Debug**.  
  
10. Zkopírujte spustitelný soubor, který jste právě vytvořili z vašeho počítače Visual Studio pro nově vytvořené složky na vzdáleném počítači.
  
    > [!CAUTION]
    >  Neprovádějte změny kódu nebo opětovné sestavení (nebo je nutné opakovat tento krok). Spustitelný soubor, který jste zkopírovali ke vzdálenému počítači se musí přesně shodovat místního zdroje a symboly.

    Můžete ručně zkopírovat na projekt, pomocí příkazu Xcopy Robocopy, prostředí Powershell nebo jiné možnosti.
  
11. Zkontrolujte, že je na cílovém počítači spuštěný vzdáleného ladicího programu (Pokud není, vyhledejte **vzdáleného ladicího programu** v **spustit** nabídky). Okno vzdáleného ladicího programu vypadá takto.  
  
     ![RemoteDebuggerWindow](../debugger/media/remotedebuggerwindow.png "RemoteDebuggerWindow")  
  
12. V sadě Visual Studio spustit ladění (**ladění > Spustit ladění**, nebo **F5**).  
  
13. Pokud se zobrazí výzva, zadejte přihlašovací údaje k síti pro připojení ke vzdálenému počítači.  
  
     Požadovaná pověření se liší v závislosti na konfiguraci zabezpečení vaší sítě. V počítači domény, můžete například zadat název domény a heslo. Na počítači nepřipojená k doméně, můžete zadat název počítače a platné uživatelské jméno účtu, jako je třeba  **MJO-DL\name@something.com** , společně s správné heslo.

     Měli byste vidět, že je hlavní okno aplikace WPF otevřít na vzdáleném počítači.
  
14. V případě potřeby proveďte akci k průchodu zarážkou. Měli byste vidět, že je aktivní bod přerušení. Pokud tomu tak není, nebyly načteny symboly pro aplikaci. Opakujte a pokud to nepomůže, získat informace o načtení symbolů a jak vyřešit potíže s jejich v [soubory symbolů principy a Visual Studio symbolů nastavení](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/05/understanding-symbol-files-and-visual-studio-s-symbol-settings.aspx).
  
15. Na počítači Visual Studio byste měli vidět, že provádění zastavil u zarážky.
  
 Pokud máte jiný kód soubory, které je potřeba použít v aplikaci, musíte zahrnout je do projektu Visual Studia. Vytvořte složku projekt pro další soubory (v **Průzkumníku řešení**, klikněte na tlačítko **Přidat > novou složku**). Pak přidat soubory do složky (v **Průzkumníku řešení**, klikněte na tlačítko **Přidat > existující položka**, vyberte soubory). Na **vlastnosti** stránky pro každý soubor, nastavte **kopírovat do výstupního adresáře** k **vždy Kopírovat**.

## <a name="set-up-debugging-with-remote-symbols"></a>Nastavení ladění se vzdálené symboly 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)   
 [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)   
 [Vzdálené ladění technologie ASP.NET v počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)