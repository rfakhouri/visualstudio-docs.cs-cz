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
ms.openlocfilehash: d7d15f2e65d30235e67fd0775684fd22e8eed0fd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>Postupy: Zabránění vypršení časových limitů u adaptérů diagnostických dat

Pokud používáte adaptérů diagnostických dat v nastavení testu, vypršení časového limitu může dojít, když spustíte test spustit z jednoho z následujících důvodů:

-   Služba řadiče testovací neběží na testovacím počítači řadiče. Možná budete muset restartovat službu. Další informace o tom, jak určit řadiči test a správa testovacích kontrolérů najdete v tématu [Správa testovací Kontroléry a testovací agenty pomocí sady Visual Studio](../test/manage-test-controllers-and-test-agents.md).

-   Pokud se shromažďování dat ve vzdáleném počítači, brána firewall může blokovat nástroje Microsoft Test Manager. Počítač, který spouští Microsoft Test Manager musíte přijmout příchozí spojení z testovacího kontroleru. Vypršení časového limitu při nástroje Microsoft Test Manager neobdrží zprávu z řadiče, protože je blokován branou firewall. Je nutné zkontrolovat nastavení brány firewall v počítači, který spouští nástroje Microsoft Test Manager. Další informace o nastavení brány firewall, viz následující [webu společnosti Microsoft](http://go.microsoft.com/fwlink/?LinkId=184980).

-   Testovací kontroler nelze vyřešit název počítače, na kterém běží Microsoft Test Manager. Tomu může dojít, pokud DNS poskytuje na nesprávnou adresu pro tento počítač. Bude pravděpodobně nutné kontaktovat správce sítě k vyřešení tohoto problému.

 Když spustíte dlouho test, který musí shromažďovat velké množství dat, je možné, že shromažďováním těchto dat časového limitu. Následující postup slouží k vyřešení tohoto problému.

 Aktualizace konfiguračního souboru pro Microsoft Test Manager nebo konfiguračního souboru pro test agent, který je vypršel časový limit, může zvýšit časový limit.

 Nástroje Microsoft Test Manager konfiguračního souboru se nazývá **mtm.exe.config**. Se nachází v následujícím adresáři: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

 Aktualizovat agenta test, je třeba aktualizovat následující konfigurační soubory v počítači agenta test. Všechny tyto soubory jsou umístěny v počítači agenta test ve stejném adresáři: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

-   QTAgent.exe.config

-   QTAgent32.exe.config

-   QTDCAgent.exe.config

-   QTDCAgent32.exe.config

 Spouštění manuálních testů a shromažďovat data z prostředí, když je vytvořena chyby nebo dokončení testovacího případu, se všechna data, která shromáždil adaptérů diagnostických dat přenese do počítače, který běží manuálních testů. Pokud jste shromáždili velké množství dat nebo mají pomalé síťové připojení, může trvat déle než výchozí hodnotu 60 sekund. Například pokud jste nakonfigurovali adaptér IntelliTrace pro shromažďování událostí IntelliTrace a volání informace pro velký počet procesů, přenos těchto dat může překročit výchozí časový limit. Tuto hodnotu zvýšit, můžete použít následující postup k aktualizaci **mtm.exe.config**.

 Chybová zpráva se zobrazí, pokud aktivita Test Runner časového limitu, nebo pokud agentem test agent vyprší časový limit. V chybové zprávě agenta test bude obsahovat informace o nástroji pro testování, které počítače agenta vypršel. Použijte následující postup k aktualizaci konfigurace souborů, v závislosti na chybovou zprávu, kterou jste přijali.

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>Pokud chcete zvýšit vypršení časových limitů pro vaše adaptérů diagnostických dat

1.  Otevřete okno Průzkumníka Windows (nebo v Průzkumníku souborů).

     Chcete-li to provést, klikněte pravým tlačítkem **spustit** a přejděte na **prozkoumat**.

    > [!NOTE]
    > Může vyžadovat oprávnění správce k aktualizaci souboru.

2.  Vyhledejte adresář v počítači *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* obsahující soubor, který je nutné aktualizovat.

3.  Klikněte pravým tlačítkem na soubor a přejděte na **otevřít v**. Vyberte editoru.

     Soubor se zobrazí v editoru. Existuje mnoho nastavení uložená v tomto souboru. Většinu těchto nastavení můžete změnit pomocí nástroje Microsoft Test Manager. Nastavení časového limitu však musíte změnit ručně, jak je popsáno v následujících krocích.

4.  Je třeba upravit v části Nastavení spuštění testu ke zvýšení hodnoty časového limitu. Tato část má následující formát:

    ```
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  Chcete-li prodloužit dobu, kterou čekat adaptérů diagnostických dat pro události, které mají být dokončena, zvyšte hodnotu pro klíč **DataCollectorEventTimeoutInSeconds**

6.  Pokud je tato chybová zpráva Časový limit aktivity pro spuštění testu, musíte zvýšit hodnotu pro klíč **RunOperationTimeoutInSeconds**.

7.  Chcete-li zvýšit časový limit pro přenos žádná data shromažďují chyby nebo při testu končí k počítači, který běží testy, je nutné přidat následující časový limit na **mtm.exe.config** v části appSettings souboru:

    ```
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > Hodnota časového limitu je v sekundách.

8.  Uložit změny, které jste provedli k souboru a znovu spusťte testy, které dříve vypršel.

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)