---
title: "Spouštět aplikace pro Windows Phone 8.1 v emulátoru | Microsoft Docs"
ms.custom: 
ms.date: 07/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c7590788-beb3-403c-a7dd-18472a9e585e
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3a5fc067ac65cea13181632c562a635599f0d7e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="run-windows-phone-81-apps-in-the-emulator"></a>Spouštět aplikace pro Windows Phone 8.1 v emulátoru
Emulátor Windows Phone poskytuje virtualizované prostředí, ve kterém můžete ladění a testování aplikací pro Windows Phone v počítači bez fyzického zařízení. Můžete simulace událostí otočení a běžné touch a zvolte velikost fyzické obrazovky a řešení, který chcete emulovat. Můžete také otestovat mnoha běžně používané funkcí, jako je například umístění, sítě, oznámení, senzorů, zrychlení a volitelné SD karty.  

Informace o spouštění Windows 10 Mobile v emulátoru, najdete v části [Test pomocí emulátoru Microsoft](/windows/uwp/debug-test-perf/test-with-the-emulator).
  
Další informace o funkcích, které můžete testovat v emulátoru Windows Phone 8.1 najdete v tématu [otestovat funkce aplikaci v emulátoru Windows Phone](http://msdn.microsoft.com/en-us/c1b2b0ec-b8cc-4a98-84c1-701428e45cb1).  
  
Emulátor společně s Visual Studio, poskytuje kompletní prostředí, ve kterém můžete navrhnout, vývoj, ladění a testování aplikace Windows Phone.  
  
##  <a name="BKMK_run"></a>Spuštění aplikace Windows Phone v emulátoru  
 Pokud vyvíjíte aplikace pro Windows Phone, můžete k nasazení a testování aplikace rychle emulátoru Windows Phone. Doporučujeme, abyste vaši aplikaci ve skutečné zařízení Windows Phone, ale před vyzkoušeli publikování aplikace v úložišti Windows Phone. Díky tomu můžete mít aplikace, protože uživatelé budou mít ji.  
  
 Při spuštění aplikace Windows Phone poprvé v emulátoru Windows Phone, dojde k následujícím událostem:  
  
1.  Spustí se emulátor.  
  
2.  Emulátor načte operační systém Windows Phone.  
  
3.  Emulátor zobrazí na obrazovce Start pro Windows Phone.  
  
4.  Aplikace je nasazený na emulátoru.  
  
5.  Vaše aplikace běží v emulátoru.  
  
 Pokud vybraný emulátor je již spuštěna, vaše aplikace je nasadit a spustit v emulátoru spuštěné. Najednou můžete spustit pouze jednu instanci každého emulátor.  
  
> [!TIP]
>  Pokud testujete aplikaci v emulátoru, ponechte emulátoru, které jsou otevřené mezi ladění relací, takže je možné aplikaci spustit znovu rychle pracovní postupy.  
  
###  <a name="BKMK_vs"></a>Spusťte aplikaci v sadě Visual Studio  
  
##### <a name="to-deploy-and-run-an-app-from-visual-studio"></a>K nasazení a spuštění aplikace ze sady Visual Studio  
  
1.  V sadě Visual Studio otevřete projekt Windows Phone.  
  
2.  Na **standardní** nástrojů, vyberte jednu z možností emulátor.  
  
     ![Seznam obrázků emulátoru Windows Phone](../debugger/media/wp_emulator_list.png "WP_Emulator_list")  
  
3.  K nasazení a spuštění aplikace s laděním, na **ladění** nabídky, klikněte na tlačítko **spustit ladění**, nebo stiskněte klávesu F5.  
  
     K nasazení a spuštění aplikace bez ladění, na **ladění** nabídky, klikněte na tlačítko **spustit bez ladění**, nebo stiskněte klávesu Ctrl + F5.  
  
     Nasazení a spuštění vaší aplikace.  
  
     K nasazení své aplikace bez spuštění, na **sestavení** nabídky, klikněte na **nasadit řešení**.  
  
##### <a name="to-stop-a-running-app"></a>Zastavit spuštěné aplikaci  
  
-   Zastavit spuštěné aplikaci, proveďte jednu z následujících akcí:  
  
    -   V sadě Visual Studio na **ladění** nabídky, klikněte na tlačítko **Zastavte ladění**, nebo stiskněte klávesu Shift + F5.  
  
    -   V emulátoru, stiskněte **zpět** tlačítko ukončete aplikaci. Pokud aktivní stránku aplikace nebyla stránka spuštění aplikace, možná budete muset stiskněte **zpět** tlačítko více než jednou.  
  
     Ukončí aplikaci a spusťte obrazovky otevře. Tím končí aktuální relaci ladění.  
  
##### <a name="to-restart-an-app-without-debugging"></a>Restartujte aplikace bez ladění  
  
1.  V emulátoru na obrazovce Start prstem zůstane k zobrazení seznamu aplikací.  
  
2.  V seznamu aplikací klepněte na ikonu aplikace. Aplikace se restartuje bez ladění.  
  
##### <a name="to-deactivate-a-running-app"></a>Postup deaktivace služby spuštěné aplikaci  
  
1.  Než spustíte aplikaci, v sadě Visual Studio, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a potom vyberte **vlastnosti** otevřete **Návrhář projektu**.  
  
2.  V **Návrhář projektu**na **ladění** ponechte **objektů označených jako neplatné po deaktivaci při ladění** políčko zaškrtnuté políčko zaškrtněte, pokud chcete aplikaci přejděte do neaktivní stav, kdy deaktivovat. Zaškrtněte políčko, pokud chcete být označené jako neplatné po deaktivaci aplikaci.  
  
3.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění**, nebo stiskněte klávesu F5 a spusťte aplikaci.  
  
4.  V emulátoru, stiskněte **spustit** tlačítko. Se zobrazí na úvodní obrazovce a aplikace je deaktivována. Aplikace buď přejde do stavu neaktivní nebo je neplatné, v závislosti na nastavení jazyka **objektů označených jako neplatné po deaktivaci při ladění** zaškrtávací políčko.  
  
##### <a name="to-reactivate-a-dormant-or-tombstoned-app"></a>Znovu aktivovat neaktivní nebo neplatné aplikace  
  
-   V emulátoru, stiskněte **zpět** tlačítko návratu do aplikace. Pokud jste přešli k ostatním stránkám nebo otevřít jiné aplikaci, bude pravděpodobně nutné stiskněte **zpět** více než jednou tlačítko znovu aktivovat aplikaci.  
  
     Obnoví relaci ladění. Ladicí program má odpojit z aplikace, budete muset stisknutím klávesy F5 obnovit relaci ladění.  
  
###  <a name="BKMK_depltool"></a>Spuštění aplikace s nástrojem pro nasazení aplikace  
 Můžete také použít nástroj pro nasazení aplikace Windows Phone (**AppDeploy.exe**) ke spouštění vaší aplikace v emulátoru. Tento nástroj je samostatná aplikace, který je nainstalován při instalaci nástrojů vývoj pro Windows Phone.  
  
 Další informace najdete v tématu [aplikací pro nasazení Windows Phone 8.1 pomocí nástroje pro nasazení aplikace](http://msdn.microsoft.com/Library/23700f82-1399-44d9-bc0c-714be4a48ee6).  
  
##  <a name="BKMK_toolbar"></a>Konfigurace emulátoru Windows Phone pomocí emulátoru panelu nástrojů  
 Tato tabulka ukazuje dostupné konfigurace tlačítek na panelu nástrojů emulátor.  
  
|Tlačítka panelu nástrojů|Možnosti konfigurace|  
|---------------------|---------------------------|  
|![Zadejte možnosti na panelu nástrojů emulátoru Windows Phone](../debugger/media/wp_emulator_.png "WP_Emulator_")|**Konfigurace bodu jeden nebo více bod vstup**<br /><br /> Když povolíte více bodu vstup, kliknete pravým tlačítkem na přesunout body touch bez zásahu na obrazovce. Klepněte na položku můžete přesunout oba body touch současně.|  
|![Orientace na panelu nástrojů emulátoru Windows Phone](../debugger/media/wp_emulator_rotation.png "WP_Emulator_rotation")|**Konfigurace orientaci emulátoru**<br /><br /> Orientace v emulátoru Windows Phone, můžete změnit na jednu ze tří orientace: výšku, šířku levé nebo pravé na šířku. Velikost emulátoru nezmění, pokud změníte orientaci.<br /><br /> Chcete-li změnit orientaci, klikněte na tlačítko **Otočit doleva** tlačítko nebo **Otočit doprava** tlačítko.|  
|![Velikost panelu nástrojů emulátoru Windows Phone](../debugger/media/wp_emulator_size.png "WP_Emulator_size")|**Nakonfigurujte velikost emulátoru**<br /><br /> Můžete změnit velikost emulátoru na obrazovce počítače hostitele. Bodů na palec (DPI) pro emulátor je založena na hostitele monitorování DPI, bez ohledu na hodnotu přiblížení.<br /><br /> – Chcete-li přizpůsobit emulátoru na obrazovku, klikněte na tlačítko **na celou obrazovku** tlačítko.<br />– Chcete-li změnit nastavení přiblížení či oddálení, klikněte **zvětšení** tlačítko. **Zvětšení** otevře se dialogové okno. V **zvětšení** dialogovém okně zadejte hodnotu přiblížení. 33 až 100.|  
  
##  <a name="BKMK_buttons"></a>Pomocí tlačítek simulované hardwaru v emulátoru  
 Pomocí tlačítka simulované hardwaru na pravé straně obrazovky emulátoru simulovat použití hardwaru tlačítek telefonu.  
  
-   Klikněte **Power** tlačítko pro simulaci a zapněte vypnutí zobrazení. Klikněte na tlačítko a podržením k simulaci vypnutí telefonu.  
  
-   Klikněte na tlačítko **svazku až** nebo **svazku dolů** tlačítko k simulaci změna objem mluvčího telefonu pro telefonní hovory a oznámení.  
  
-   **Fotoaparát** tlačítko spustí aplikaci fotoaparát. Můžete simulovat trvá fotografie nebo video s použitím ovládacích prvků v aplikaci fotoaparát.  
  
 Následující snímek obrazovky ukazuje tlačítka simulované hardwaru.  
  
1.  Levý obrázek zobrazí na úvodní obrazovce v emulátoru.  
  
2.  Střední obrázek se zobrazí po klepnutí na emulátoru **Power** tlačítko Vypnout displej.  
  
3.  Bitovou kopii správné zobrazí po klepnutí na obrazovce emulátoru **svazku až** tlačítko zvětšete svazek.  
  
 ![Tlačítka v emulátoru Windows Phone](../debugger/media/wp_emulator_buttons.png "WP_Emulator_buttons")  
  
##  <a name="BKMK_tasks_kbd"></a>Použití klávesnice počítače pomocí emulátoru  
 Emulátoru podporuje mapování klávesnice hardware ve svém vývojovém počítači na klávesnici na Windows Phone. Chování klíče je stejné jako u zařízení s Windows Phone.  
  
 Ve výchozím nastavení není povoleno klávesnice hardwaru. Tato implementace je stejná jako posuvné klávesnice, který musí být nasazené, než budete moci použít. Před povolením klávesnice hardwaru emulátoru přijímá klíče vstup pouze z ovládacího prvku klíče.  
  
 Speciální znaky na klávesnici lokalizované verze vývojovém počítači Windows nepodporuje emulátor. Chcete-li zadat speciální znaky, které se nacházejí na lokalizované klávesnice, použijte Panel vstup softwaru (SIP).  
  
 Použití klávesnice počítače v emulátoru, stisknutím klávesy PAGE UP klíč nebo klíč PAUSE/BREAK (emulátor systému Windows 8 nebo 8.1) nebo F4 (emulátoru Windows 10).  
  
 Chcete-li zastavit pomocí klávesnice počítače v emulátoru, stiskněte klávesy PAGE DOWN klíč nebo klíč PAUSE/BREAK (emulátor systému Windows 8 nebo 8.1) nebo F4 (emulátoru Windows 10).  
  
 Následující tabulka uvádí klíče na klávesnici hardwaru, můžete emulovat tlačítek a jiných ovládacích prvků na Windows Phone.  
  
|Hardwarový klíč počítače|Windows Phone hardwarové tlačítko.|Poznámky|  
|---------------------------|-----------------------------------|-----------|  
|F1|ZPĚT|Dlouhé stisknutí fungovat podle očekávání.|  
|F2|SPUŠTĚNÍ|Dlouhé stisknutí fungovat podle očekávání.|  
|F3|HLEDÁNÍ||  
|F4|V emulátoru Windows 10 Přepne mezi pomocí klávesnice v místním počítači a není pomocí klávesnice v místním počítači.|Není k dispozici v emulátoru systému Windows 8 nebo 8.1.|  
|F5|Nelze použít.||  
|F6|FOTOAPARÁT POLOLETÍ|Tlačítko vyhrazené fotoaparát, které stisknutí uprostřed.|  
|F7|ÚPLNÉ FOTOAPARÁT|Tlačítko vyhrazené fotoaparát.|  
|F8|Nelze použít.||  
|F9|SVAZEK NAHORU||  
|F10|SVAZEK DOLŮ||  
|F11|Nelze použít.||  
|F12|NAPÁJENÍ|Stisknutím klávesy F12 dvakrát povolit zamykací obrazovce.<br /><br /> Dlouhé stisknutí fungovat podle očekávání.|  
|ESC|ZPĚT|Dlouhé stisknutí fungovat podle očekávání.|  
|POZASTAVENÍ NEBO PŘERUŠENÍ|Přepnutí klávesnice (pouze emulátor systému windows 8 nebo 8.1).|Není k dispozici pro emulátor sady Windows 10.|  
|PAGE UP|Umožňuje pomocí klávesnice hardwaru (pouze emulátor systému Windows 8 nebo 8.1).|Není k dispozici pro emulátor sady Windows 10.|  
|PAGE DOWN|Zakáže klávesnice hardwaru (pouze emulátor systému Windows 8 nebo 8.1).|Není k dispozici pro emulátor sady Windows 10.|  
  
##  <a name="BKMK_checkpoints"></a>Uložení a načtení vlastní kontrolní body  
 Uložte snímek stavu v emulátoru pomocí **kontrolní body** kartě v emulátoru **další nástroje**. Tato funkce je užitečná, pokud často testování aplikace s stejná data a nastavení.  
  
 Například pokud aplikace vyžaduje několik kontakty, můžete vytvořit záznamy kontaktů jednou a uložte snímek emulátor. V opačném případě budete muset znovu vytvořit záznamy kontaktů pokaždé, když spusťte emulátor.  
  
-   Klikněte na tlačítko **nového kontrolního bodu** k zachycení nový snímek stavu emulátoru s daty a nastavení požadované k testování aplikace znovu později. K přidání nového kontrolního bodu **kontrolní body** seznamu.  
  
     Kontrolní bod nelze zaznamenat, zatímco ladicího programu je připojen k emulátoru.  
  
-   Vyberte kontrolní bod v **kontrolní body** seznamu zobrazíte informace o kontrolního bodu.  
  
-   Vyberte přepínač v **výchozí** sloupec aby uložené kontrolní bod výchozí kontrolní bod pro aktivní emulátor.  
  
-   Klikněte na tlačítko **obnovení** restartovat operační systém Windows Phone v emulátoru a načíst vybraný snímek.  
  
-   Klikněte na tlačítko **odstranit** odstranit snímek, který už nepotřebujete.  
  
 Původní bitové kopie emulátoru vždy zobrazí jako první položky **kontrolní body** seznamu a nelze změnit ani odstranit. Ale můžete vybrat jiný snímek jako výchozí emulátor image.  
  
 ![Karta kontrolní body emulátoru Windows Phone](../debugger/media/wp_emulator_checkpoints.png "WP_Emulator_checkpoints")  
  
##  <a name="BKMK_tasks_shot"></a>Zachycení snímků obrazovky v emulátoru  
 Snímky obrazovky aplikace pro Windows Phone můžete vytvořit pomocí nástroje snímek z okna Další nástroje. Nástroj vytvoří soubory PNG, které odpovídají na řešení spuštěného emulátoru.  
  
 ![Snímky obrazovky z Windows Phone emulátoru](../debugger/media/wp_emulator_screenshots.png "WP_Emulator_screenshots")  
  
#### <a name="to-create-an-app-screenshot-by-using-the-built-in-emulator-screenshot-tool"></a>Chcete-li vytvořit – snímek obrazovky aplikace pomocí nástroje předdefinované emulátoru – snímek obrazovky  
  
1.  K optimalizaci kvality vaše snímky obrazovky, nastavení úrovně přiblížení emulátoru do 100 procent. Tím vyšší nastavení úrovně přiblížení, tím lépe kvality na snímku obrazovky.  
  
2.  Spusťte aplikaci v emulátoru.  
  
3.  Na panelu nástrojů emulátor, klikněte na tlačítko Rozšířené otevřete **další nástroje** okno.  
  
4.  Klikněte **– snímek obrazovky** kartě.  
  
5.  Když je aplikace připravená, klikněte **zaznamenat** tlačítko.  
  
     Na snímku obrazovky se zobrazí v pracovním prostoru.  
  
6.  Klikněte **Uložit** tlačítko Otevřít **uložit jako** dialogové okno.  
  
7.  Vyberte umístění a **název souboru** a pak klikněte na tlačítko **Uložit**.  
  
8.  Volitelně můžete přejít na jiné stránky v aplikaci a zachycení další snímky obrazovky.  
  
9. Spusťte emulátor s jinou rozlišení k zachycení stejné snímky obrazovky v jiné rozlišení. Pokud jste spustili aplikaci s laděním, budete muset Zastavte ladění předtím, než můžete ji spustit znovu na jiné emulátor.  
  
 Zakážete čítače míra rámce na obrazovce emulátoru ještě před zaznamenáním snímky obrazovky, které bude odeslána do úložiště Windows Phone.  
  
#### <a name="to-disable-frame-rate-counters-in-the-emulator-before-capturing-screenshots"></a>Chcete-li zakázat čítače míra rámce v emulátoru před zachycením snímky obrazovky  
  
-   Zadejte sestavení pro vydání v sadě Visual Studio. Po zadání sestavení pro vydání, spusťte aplikaci tak, že vyberete **nasadit *[název aplikace]***  odkaz na **sestavení** nabídky.  
  
-   Alternativně můžete Zakomentovat řádek kódu v souboru app.xaml.cs nebo app.xaml.vb, který nastaví hodnotu `EnableFrameRateCounter` k `true`.