---
title: Přidání kontextových parametrů k parametrům spuštění testu zatížení v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, context parameters
- load tests, context parameters
ms.assetid: a8a0b97e-8040-4711-85ab-36548b130ed2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: dd19f945dec052ad2c90784252c0c85eba6889ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-context-parameters-to-a-load-test-run-setting"></a>Postupy: Přidání kontextových parametrů k parametrům spuštění zátěžového testu

Jakmile vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

Kontextové parametry používat v zátěžovém testu spusťte nastavení pomocí editoru načíst testování můžete vytvořit. Kontextové parametry umožňují Parametrizace řetězec.

Předpokládejme, že zátěžového testu obsahuje testu výkonnosti webu, který už používá parametrizované adresy URL webového serveru pomocí kontext parametru. Kontext parametru můžete přidat k zátěžovému testu spusťte nastavení, která používá stejnou hodnotu pro název jako ten, který se používá v testu výkonnosti webu. Při spuštění zátěžového testu to bude mapovat testu výkonnosti webu na jiný server. Například pokud zatížení testování zahrnuje testu výkonnosti webu, který používá kontext parametru, který je pojmenován Webový_server1 pro název webového serveru v adrese URL. Pokud zadáte v testu zatížení spusťte nastavení, která se také nazývá Webový_server1 pak kontext parametru zátěžový test použije parametr kontext, který jste přiřadili v parametrech běhu zátěžového testu. O vysvětlení, pokud testu výkonnosti webu v zátěžovém testu používá stejný název parametru kontextu jako parametr kontextu v zátěžovém testu, přepíše kontext parametru v zátěžovém testu kontext parametru, který se používá v testu výkonnosti webu.

> [!WARNING]
> Dejte pozor, abyste neúmyslně přepsat kontext parametru testu výkonnosti webu, při použití kontextových parametrů v parametrech běhu. Nepoužívejte stejné názvy parametrů kontextu, pokud to uděláte záměrně.

Pokud přiřadíte hodnotu parametru kontextu webový_server1 `http://CorporateStagingWebServer`, pak můžete použít `WebServer1` v celé zatížení testování a tím snadno kdykoli změnit hodnotu na jiný webový server.

Kromě toho přiřazením různé hodnoty na parametr kontextu za použití stejného názvu v nastavení testu různé zatížení můžete spustit zátěžový test pomocí různých prostředích:

-   Podnikový Web Server pracovní spustit nastavení: kontext parametru, který je pojmenován Webový_server1 =http://CorporateStagingWebServer

-   Nastavení spuštění podnikové produkční webový Server: Parametr kontextu, který je s názvem Webový_server1 =http://CorporateProductionWebServer

 **Změna nastavení spuštění z příkazového řádku**

 Pokud chcete využít výhod strategie parametr kontextu pomocí různých nastavení spuštění z příkazového řádku, použijte následující příkazy:

 **Set Test.UseRunSetting= CorporateStagingWebServer**

 - a -

 **/testcontainer:loadtest1.loadtest mstestu**

## <a name="to-add-a-context-parameter-to-a-run-setting"></a>Chcete-li přidat parametr kontextu k parametrům spuštění

1.  Otevřete zátěžový test.

2.  Rozbalte **spustit nastavení** složku ve stromu testu zatížení v editoru načíst otestovat.

3.  Klikněte pravým tlačítkem na konkrétním spustit nastavení na který chcete přidat parametr kontextu a potom zvolte **přidat parametr kontextu**.

     Přidán nový parametr kontextu **kontextové parametry** složky v **spustit nastavení** složky ve stromu testu zatížení.

     -nebo-

     Pokud spustit nastavení již obsahuje **kontextové parametry** složky, můžete ho klikněte pravým tlačítkem a pak zvolte **přidat parametr kontextu**.

4.  V okně vlastností změňte hodnotu **název** podle potřeby (například Webový_server1). V okně vlastností změňte **hodnotu** na parametr, který chcete použít (například http://CorporateStagingWebServer).

5.  (Volitelné) Zopakujte kroky 3 až 5 a použít jiný řetězec pro **hodnotu** vlastnosti (například http://CorporateProductionWebServer).

6.  Zvolte, které spustit nastavení, které chcete být aktivní. Otevřete místní nabídky na spuštění nastavení a vyberte **nastavená jako aktivní**.

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)