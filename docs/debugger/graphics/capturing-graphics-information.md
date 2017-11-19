---
title: "Zaznamenání grafických informací | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.frame
- vs.graphics.capturewindow
- VS.ToolsOptionsPages.Graphics_Diagnostics.Capture
ms.assetid: 187ce86e-e340-4f6c-8937-8e8f1027a17f
caps.latest.revision: "41"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68e02e99eb621a5f7884e9848f0065fa0220be92
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="capturing-graphics-information"></a>Zaznamenání grafických informací
Zaznamenání grafických informací z aplikace Direct3D – tak, aby Visual Studio Graphics Analyzer můžete použít k diagnostikování problémů vykreslování a problémy s výkonem.  
  
## <a name="capturing-graphics-information"></a>Zachycení informací grafiky  
 Zachycení informací grafiky je dvoustupňový proces. Nejprve spusťte aplikaci v rámci Diagnostiky grafiky a následně určete jeden nebo více snímků, ze kterých budou zachyceny podrobné informace.  
  
### <a name="to-run-your-app-under-graphics-diagnostics"></a>Spuštění aplikace v rámci Diagnostiky grafiky  
  
-   Na řádku nabídek zvolte **ladění**, **grafiky**, **spustit ladění grafiky**. (Klávesnice: stiskněte klávesy Alt + F5)  
  
-   Na **grafiky** nástrojů, vyberte **spustit ladění grafiky** tlačítko.  
  
 Když je aplikace spuštěna v rámci Diagnostiky grafiky, některé druhy informací grafiky jsou zachycovány neustále. Patří mezi ně nastavení zařízení, vytváření řetězce přepnutí, vytváření grafických objektů a zdrojů a další důležité události, které ovlivňují více než jeden snímek. Zároveň můžete zachytit podrobné informace o konkrétních snímcích. Jedná se například o volání draw a rozesílání počítačového shaderu a objekty Direct3D a zdroje, které je podporují.  
  
### <a name="to-capture-a-frame"></a>Zachycení snímku  
  
-   V sadě Visual Studio na **grafiky** nástrojů, klikněte na tlačítko **zachycení rámce** tlačítko ![grafiky zaznamenat tlačítko ikonu](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics").  
  
-   Na klávesnici stiskněte klávesu Print Screen.
  
    > [!NOTE]
    >  Když aplikace běží pod **diagnostiky grafiky**, klíč Print Screen. lze použít pouze k zachycení snímku grafických informací; neprovede jeho normální funkce. To platí, dokud neukončíte zachycování informací grafiky – obvykle zastavením ladění nebo standardním ukončením aplikace, a to i když je aktivní jiná aplikace.  
  
-   V sadě Visual Studio zachycení rozhraní zvolili **zachycení rámce** tlačítko nacházel pod **relace diagnostiky** časové osy, nebo zvolte velké **zachycení rámce** tlačítko nacházel pod **snímků za sekundu** swim dráhy a doprava všechny dříve zachycení snímků. Obě tlačítka jsou vyznačené na obrázku níže.  
  
     ![Zaznamenání pomocí nástroje využití GPU rámce.](media/pix_gpu_usage_tool_capture_frame.png)  
  
     Až budete připraveni k prozkoumání snímky jste zaznamenali, spusťte **Visual Studio Graphics Analyzer** podle **rámce...**  propojení nad miniatur bitovou kopii nebo poklepáním na miniaturu.  
  
 Pouze celý rámce se dají zachytit, tak při zahájení zachycení, je ve skutečnosti grafických informací z další rámce, který je zaznamenán. Záznam začne okamžitě po zobrazení snímku, ve kterém jste zachycování inicializovali, a ukončí se po zobrazení zachyceného snímku. Když je aplikace spuštěna v rámci Diagnostiky grafiky, můžete zachytit libovolný počet snímků. Pokud nezachytíte žádné snímky, protokol grafiky bude zrušen.  
  
 Při zachytávání snímků, Visual Studio zobrazí okno diagnostiky relace (.diagsession). Pokud toto okno zavřít, zastavte ladění nebo zavřete aplikaci, nemůže zaznamenat všechny další snímky pro tento protokol. K zaznamenání grafických informací další, budete muset spustit aplikaci v rámci diagnostiky grafiky znovu se nová relace diagnostiky.  
  
### <a name="graphics-diagnostics-capture-options"></a>Možnosti zachycení diagnostiky grafiky  
 Můžete nakonfigurovat zachycení shromažďovat zásobníky volání pro všechny události grafiky nebo podmnožinu omezená, zakázat zachytávání HUD a povolit nebo zakázat režim kompatibility zachytávání.  
  
#### <a name="to-configure-graphics-diagnostics-capture-options"></a>Konfigurace možností zachycení diagnostiky grafiky  
  
1.  V řádku nabídek zvolte Nástroje, možnosti. Zobrazí se dialogové okno Možnosti.  
  
2.  V seznamu kategorií možnosti na levé straně vyberte diagnostiky grafiky, a potom nakonfigurujte možnosti diagnostiky grafiky, které chcete.  
  
     **Během zachycení shromažďovat zásobníky volání (díky zaznamenat něco pomalejší)**  
     Zaškrtnutím tohoto políčka shromažďovat zásobníky volání. Ve výchozím nastavení nejsou shromážděna zásobníky volání. K zachycení zásobníky volání, ujistěte se, že **hovor balíků během zachycení (díky zaznamenat něco pomalejší** zaškrtávací políčko je nastaven na povolte kolekce a nastavte buď **pro kreslení, odesílání, přítomen a výkonu označení**shromažďovat jenom nejdůležitější zásobníky volání, možnost (výchozí) nebo **všem** možnost ke shromažďování všech zásobníky volání. Chcete-li zastavit shromažďování zásobníky volání později, zrušte **hovor balíků během zachycení (díky zaznamenat něco pomalejší** zaškrtávací políčko.  
  
     **Zakázat ve hře HUD během zachycení**  
     Zkontrolujte, zda toto políčko Zakázat HUD překrytí, které aplikace spuštěna pod grafiky diagnostiky obvykle zobrazí. Zrušte zaškrtnutí políčka Zobrazit překrytí HUD.  
  
     **Zaznamenat v režimu kompatibility**  
     Zaškrtněte toto políčko k zaznamenání grafických informací v režimu kompatibility. Zaznamenání v režimu kompatibility je výchozí. V režimu kompatibility nebudou podávat Direct3D –, že na grafický procesor s podporuje všechny další funkce nad rámec těch, definované na úrovni základní funkce. To brání aplikaci zaznamenávané pomocí hardwaru rozšíření na grafický procesor s jeho zaznamenané v a zajišťuje lze přehrát protokol grafiky zpět pomocí žádné grafický procesor, který podporuje funkce stejná nebo vyšší úrovni. Zrušte zaškrtnutí tohoto políčka Zakázat režim kompatibility; protokoly zachytit pomocí režimu kompatibility zakázáno se nepodaří přehrání na všechny grafický procesor, která nepodporuje stejné další funkce, které byly použity aplikace během zachycení.  
  
     **Zastavit sběr dat při výskytu chyb vrstvy jakékoli SDK**  
     Zaškrtnutím tohoto políčka zastavení zachycení okamžitě, pokud dojde k chybám.  
  
## <a name="capturing-graphics-information-remotely"></a>Vzdálené zachycení informací grafiky  
 Informace grafiky lze zaznamenat z aplikace, která je spuštěna v místním počítači nebo ve vzdáleném počítači či zařízení. Vzdálené zachycení je podporována pro [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)] počítače a [!INCLUDE[winblue_winrt_2](../includes/winblue_winrt_2_md.md)] zařízení. Chcete-li zachytit informace grafiky z aplikace, která je spuštěna vzdáleně, nakonfigurujte svůj projekt na vzdálené ladění a spusťte aplikaci v rámci Diagnostiky grafiky, jak bylo popsáno dříve. Aplikace se spustí ve vzdáleném počítači a zachycené informace grafiky se zaznamenají do vývojového počítače.  
  
 Konfigurace projektu pro vzdálené ladění závisí na typu aplikace, kterou vyvíjíte, a používaném programovacím jazyku. Informace o konfiguraci vzdáleného ladění pro aplikace pro UPW najdete v tématu [aplikace UWP spustit na vzdáleném počítači](../run-windows-store-apps-on-a-remote-machine.md). Informace o konfiguraci vzdáleného ladění pro aplikace na ploše systému Windows najdete v tématu [vzdálené ladění](../remote-debugging.md).  
  
 Později lze vzdálený počítač nebo zařízení použít k přehrání informací grafiky bez ohledu na to, odkud byly informace zachyceny. Další informace najdete v tématu [postupy: Změna počítače pro přehrávání diagnostiky grafiky](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="capturing-graphics-information-from-the-command-line"></a>Zaznamenání grafických informací z příkazového řádku  
 Můžete zaznamenat grafických informací z aplikace pomocí nástroje příkazového řádku. Tento nástroj DXCap.exe, můžete rychle zachytit a přehrání grafických informací bez použití sady Visual Studio nebo zachytávání prostřednictvím kódu programu. Můžete konkrétně DXCap.exe pro automatizaci nebo v testovacím prostředí. Další informace o DXCap.exe najdete v tématu [zaznamenat nástroj příkazového řádku](command-line-capture-tool.md)  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zaznamenání grafických informací](walkthrough-capturing-graphics-information.md)