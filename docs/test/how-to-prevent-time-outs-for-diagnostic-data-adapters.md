---
title: Vypršení časových limitů u adaptérů diagnostických dat v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, increasing time-outs
ms.assetid: 39fff4fc-9233-4f67-96ac-e81bbaf7ca82
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 8359aa76dc2f62afb63f6a36984492210d9aeeff
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39380011"
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>Postupy: zabránění vypršení časových limitů u adaptérů diagnostických dat

Pokud používáte adaptéry diagnostických dat ve vašem nastavení testu, vypršení časového limitu může dojít při spuštění testů z jednoho z následujících důvodů:

-   Služba testovací kontrolér není spuštěna v počítači řadiče testu. Budete muset restartovat službu. Další informace o způsobu určení testovacího kontroléru a spravovat kontrolery testů naleznete v tématu [Správa testovacích kontrolérů a testovacích agentů v sadě Visual Studio](../test/manage-test-controllers-and-test-agents.md).

-   Pokud shromažďujete data na vzdáleném počítači, brána firewall může blokovat nástroje Microsoft Test Manager. Počítač, na kterém běží Microsoft Test Manager musíte přijmout příchozí připojení z kontroleru testů. Vypršení časového limitu vyvolá se v případě nástroje Microsoft Test Manager neobdrží zprávu z řadiče, protože je blokován branou firewall. Je třeba zkontrolovat nastavení brány firewall na počítači, na kterém běží Microsoft Test Manager.

-   Testovací kontrolér nemůže přeložit název počítače, na kterém běží Microsoft Test Manager. Tato situace může nastat, pokud služba DNS poskytuje nesprávnou adresu pro tento počítač. Budete muset kontaktovat správce sítě k vyřešení tohoto problému.

Při spuštění dlouhého testu, který musí shromáždit velké množství dat, můžete zjistit, že se shromažďováním těchto dat vyprší časový limit. Následující postup slouží k vyřešení tohoto problému.

Můžete zvýšit časový limit aktualizací konfiguračního souboru pro Microsoft Test Manager nebo konfiguračního souboru pro testovacího agenta, který je vypršení časového limitu.

Nástroje Microsoft Test Manager konfigurační soubor nazývá *mtm.exe.config*. Je umístěn v následujícím adresáři: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

Pokud chcete aktualizovat testovacího agenta, je nutné aktualizovat následující konfigurační soubory v počítači testovacího agenta. Všechny tyto soubory jsou umístěny v počítači testovacího agenta ve stejném adresáři: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

-   *QTAgent.exe.config*

-   *QTAgent32.exe.config*

-   *QTDCAgent.exe.config*

-   *QTDCAgent32.exe.config*

Pokud spuštění manuálních testů a shromažďování dat z prostředí, při vytvoření chyby nebo dokončení testovacího případu, přenese se všechna data, která byla shromážděna adaptéry diagnostických dat na počítači, který spouští ruční testy. Pokud jste shromáždili velké množství dat nebo máte pomalé připojení k síti, může trvat déle, než je výchozí hodnota 60 sekund. Například pokud jste nakonfigurovali adaptér IntelliTrace ke shromáždění události IntelliTrace a volali informace pro mnoho procesů, přenos těchto dat může překročit výchozí časový limit. Tuto hodnotu zvýšit, můžete použít následující postup aktualizovat *mtm.exe.config*.

Pokud vyprší časový limit nástroje Test Runner nebo testovacího agenta vyprší časový limit, zobrazí se chybová zpráva. Chybová zpráva pro testovací agent bude obsahovat informace, o které testovací počítače agenta vypršení časového limitu. Použijte následující postup k aktualizaci konfiguračních souborů, v závislosti na chybovou zprávu jste obdrželi.

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>Zvýšení časových limitů pro adaptéry diagnostických dat

1.  Otevřete okno Průzkumníka Windows (nebo Průzkumníka souborů).

     Chcete-li to provést, klikněte pravým tlačítkem na **Start** a přejděte na **prozkoumat**.

    > [!NOTE]
    > Budete potřebovat oprávnění správce k aktualizaci souboru.

2.  Vyhledejte adresář v počítači *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* , která obsahuje soubor, který je nutné aktualizovat.

3.  Klikněte pravým tlačítkem na soubor a přejděte na **otevřít v**. Vyberte editor.

     Soubor se zobrazí v editoru. Existuje mnoho nastavení uložených v tomto souboru. Většinu těchto nastavení můžete změnit pomocí nástroje Microsoft Test Manager. Nastavení časového limitu však musíte změnit ručně, jak je popsáno v následujících krocích.

4.  Je třeba upravit oddíl nastavení spouštění testu ke zvýšení hodnot časového limitu. Tato část má následující formát:

    ```text
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  Pokud chcete zvýšit dobu, po kterou adaptéry diagnostických dat čekat na dokončení událostí, zvyšte hodnotu pro klíč **DataCollectorEventTimeoutInSeconds**.

6.  Pokud chybová zpráva vypršení časového limitu je pro aktivitu nástroje Test Runner, musíte zvýšit hodnotu pro klíč **RunOperationTimeoutInSeconds**.

7.  Pokud chcete zvýšit časový limit pro přenos dat shromážděných pro chybu nebo při ukončení testu k počítači, na kterém běží testy, je nutné přidat následující časový limit do *mtm.exe.config* v oddíle appSettings souboru:

    ```text
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > Hodnota časového limitu je během několika sekund.

8.  Uložit změny provedené k souboru a znovu spusťte testy, které dříve vypršel.

## <a name="see-also"></a>Viz také:

- [Shromažďování diagnostických údajů pomocí nastavení testů](../test/collect-diagnostic-information-using-test-settings.md)