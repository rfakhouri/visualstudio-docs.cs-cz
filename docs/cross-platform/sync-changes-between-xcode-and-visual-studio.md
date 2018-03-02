---
title: "Synchronizovat změny mezi XCode a Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c71a4d7c-120e-4559-a114-3a99c4b860a9
ms.technology: vs-ide-mobile
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 8c18767c6fb711c6ccdc35caab57518d26f0188d
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="sync-changes-between-xcode-and-visual-studio"></a>Synchronizace změn mezi XCode a Visual Studio
Microsoft Visual C++ pro vývoj mobilních řešení pro součást obsahuje vzdálené funkce pro synchronizaci práci mezi vaším Počítačem a vaše Mac. Pokud vaše prostředí Visual Studio a Mac počítače jsou spárovat, jsou k dispozici pro iOS aplikace projekty v sadě Visual Studio, který vám pomůže, otevřete projekt v XCode, nové možnosti přesunutí kódu mezi XCode a Visual Studio a vyčistit dočasný adresář projektu XCode.  
  
 Použití možností vzdáleného počítače, musí být projektu projekt aplikace iOS, a Visual Studio musí být spárována s vaší Mac. Požadavky a pokyny, jak pár Mac najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
## <a name="the-remote-machine-menu"></a>V nabídce vzdáleného počítače  
 V **Průzkumníku**, klikněte pravým tlačítkem na projekt aplikace iOS k zobrazení v místní nabídce. Vyberte **vzdáleného počítače** položka vzdálené možnosti, které jsou k dispozici.  
  
 ![Položky nabídky vzdáleného počítače v Průzkumníku řešení](../cross-platform/media/cppmdd_u2_remotemachine_menu.jpg "CPPMDD_U2_RemoteMachine_Menu")  
  
 Tyto příkazy umožňují otevřete projekt v XCode, přesuňte místní změny nebo celý projekt mezi sadou Visual Studio a XCode a vyčistit dočasné soubory na vzdáleném počítači.  
  
### <a name="open-in-xcode"></a>Otevřít v XCode  
 Otevřete projekt v XCode ze sady Visual Studio na **vzdáleného počítače** podnabídky, zvolte **otevřít v XCode** otevřít vybraný projekt na spárované vzdáleného počítače. Vcremote server slouží k otevření XCode na počítači Mac a přejděte do dočasného adresáře na počítači Mac, který obsahuje kopii projektu vytvořit. Visual Studio se zobrazí dialogové okno, které ukazuje název dočasného adresáře pro projekt. Akce prováděné na vzdáleném počítači jsou také uvedené v **výstup** oken v sadě Visual Studio. K jejich zobrazení, možná budete muset vybrat možnost **Visual C++ vzdáleného počítače** v **zobrazit výstup z** rozevírací seznam v horní části **výstup** okno.  
  
 ![Ve výstupním okně zobrazí akce vzdáleného počítače. ] (../cross-platform/media/cppmdd_u2_remotemachine_output.png "CPPMDD_U2_RemoteMachine_Output")  
  
 Na počítači Mac můžete pomocí všech nástrojů XCode upravit kód a prostředky, scénářů a akce. V sadě Visual Studio je váš projekt aplikace iOS označena "Otevřít v XCode" k označení, že ve vzdáleném počítači mohou být provedeny změny. Po dokončení úprav se můžete vyžádání ze vzdáleného nebo přírůstkové načítat z vzdálené příkazy ke zkopírování změny zpět do projektu sady Visual Studio.  
  
### <a name="push-to-remote-and-incremental-push-to-remote"></a>Nabízená vzdálené a přírůstkové nabízené vzdálené  
 Pokud provedete změny do projektu iOS aplikace v sadě Visual Studio, nabízená instalace vzdáleného a přírůstkové nabízená vzdálené příkazy slouží k přesunutí souborů změněné projektu spárované vzdáleného počítače. Nabízeného oznámení do vzdáleného příkazu zkopíruje všechny soubory projektu do vzdáleného počítače. Přírůstkové Push na vzdálený příkaz zkopíruje pouze změněné soubory do vzdáleného počítače. U velkých projektů s menší změny můžete uložit příkaz přírůstkové čas a šířku pásma.  
  
 Kopírování souborů projektu do počítače Mac v sadě Visual Studio v **Průzkumníku řešení** okna, klikněte pravým tlačítkem na projekt aplikace iOS otevřít v místní nabídce. Vyberte **vzdáleného počítače** a zvolit buď **Push vzdálené** nebo **přírůstkové Push vzdálené** pro kopírování souborů projektu ze sady Visual Studio do vaší Mac.  
  
### <a name="pull-from-remote-and-incremental-pull-from-remote"></a>Ze vzdáleného a přírůstkové vyžádaných ze vzdáleného pro vyžádání obsahu  
 Když provedete změny do projektu v XCode, přesunete změny zpět do Visual Studio pro synchronizaci projektů.  
  
 Kopírování souborů projektu z počítače Mac v sadě Visual Studio v **Průzkumníku řešení** okna, klikněte pravým tlačítkem na projekt aplikace iOS otevřít v místní nabídce. Vyberte **vzdáleného počítače** a zvolit buď **načítat z vzdálené** nebo **přírůstkové načítat z vzdálené** pro kopírování souborů projektu z počítače Mac do sady Visual Studio.  
  
### <a name="clean-remote"></a>Vyčištění vzdálené  
 Vyčištění dálkového příkazu můžete odstranit soubory v adresáři projektu dočasné ve vzdáleném počítači. Obsah adresáře, včetně žádné zdrojové soubory nebo sestavení produkty, jsou odebrány vaše Mac. Ujistěte se, že proběhla všechny změny, které chcete zachovat zpět k sadě Visual Studio pomocí přijetí změn ze vzdáleného nebo přírůstkové načítat z vzdálené dříve, než použijete příkaz vyčištění vzdálené.  
  
 Pro čištění adresáři dočasné projektu ve vzdáleném počítači, v sadě Visual Studio v **Průzkumníku řešení** okna, klikněte pravým tlačítkem na projekt aplikace iOS otevřít v místní nabídce. Vyberte **vzdáleného počítače** a zvolte **čisté vzdálené** odebrat soubory adresáře projektu z vaší Mac.