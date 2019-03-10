---
title: Přiřazení portů vzdáleného ladicího programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 05/18/2018
ms.topic: reference
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 672d54b29e6de9302e88b1b95b4117783b8a0113
ms.sourcegitcommit: 1024f336dcd8e8a4c50b9a9ad8ec85b6e70073a8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57699613"
---
# <a name="remote-debugger-port-assignments"></a>Přiřazení portů vzdáleného ladicího programu
Visual Studio Remote Debugger může běžet jako aplikace nebo jako službu na pozadí. Při spuštění jako aplikace, používá port, který je přiřazen ve výchozím nastavení následujícím způsobem:
::: moniker range=">=vs-2019"
- Visual Studio 2019: 4024
::: moniker-end
- Visual Studio 2017: 4022

- Visual Studio 2015: 4020

- Visual Studio 2013: 4018

- Visual Studio 2012: 4016

  Jinými slovy číslo portu přiřazené vzdálený ladicí program je zvýšen o 2 pro každou vydanou verzí. Můžete nastavit jiné číslo portu, jako je. Vysvětlíme, jak nastavit čísla portů v další části.

## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>Portu vzdáleného ladicího programu na 32bitové operační systémy

::: moniker range=">=vs-2019"
 4024 TCP (ve Visual Studio 2019) je hlavní port a pro všechny scénáře se vyžaduje. To můžete nakonfigurovat z příkazového řádku nebo v okně vzdáleného ladicího programu.
::: moniker-end
::: moniker range="vs-2017"
 TCP 4022 (v sadě Visual Studio 2017) je hlavní port a pro všechny scénáře se vyžaduje. To můžete nakonfigurovat z příkazového řádku nebo v okně vzdáleného ladicího programu.
::: moniker-end

 V okně vzdáleného ladicího programu klikněte na tlačítko **nástroje > Možnosti**a nastavte číslo portu TCP/IP.

 Na příkazovém řádku spustit vzdálený ladicí program se **portu/** přepnout: **msvsmon/port \<číslo portu >**.

 Můžete najít vzdálený ladicí program přepínače příkazového řádku v nápovědě vzdáleného ladění (stisknutím klávesy **F1** nebo klikněte na tlačítko **Nápověda > využití** v okně vzdáleného ladicího programu).

## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>Portu vzdáleného ladicího programu na 64bitové operační systémy
::: moniker range=">=vs-2019"
 Při spuštění 64bitovou verzi vzdáleného ladicího programu, používá hlavní portu (4024) ve výchozím nastavení.  Pokud ladíte 32bitový proces, spustí 64bitovou verzi vzdáleného ladicího programu 32bitovou verzi vzdáleného ladicího programu na portu 4025 (číslo portu hlavní zvyšuje o 1). Při spuštění vzdáleného ladicího programu 32-bit, používá 4024 a 4025 nepoužívá.
::: moniker-end
::: moniker range="vs-2017"
 Při spuštění 64bitovou verzi vzdáleného ladicího programu, používá hlavní port (4022) ve výchozím nastavení.  Pokud ladíte 32bitový proces, spustí 64bitovou verzi vzdáleného ladicího programu 32bitovou verzi vzdáleného ladicího programu na port 4023 (číslo portu hlavní zvyšuje o 1). Při spuštění vzdáleného ladicího programu 32-bit, používá 4022 a 4023 se nepoužijí.
:::moniker-end

 Tento port jde nakonfigurovat z příkazového řádku: **Msvsmon/wow64port \<číslo portu >**.

## <a name="the-discovery-port"></a>Port zjišťování
 UDP 3702 slouží k vyhledání spuštěné instance vzdáleného ladícího programu v síti (například **najít** dialogového okna v **připojit k procesu** dialogového okna). Používá se pouze pro zjišťování počítači se systémem vzdálený ladicí program, takže je volitelný, pokud máte nějaké další způsob, jak zjistit název počítače nebo IP adresu cílového počítače. Jedná se standardním portem pro zjišťování, proto není možné nakonfigurovat číslo portu.

 Pokud nechcete povolit zjišťování, můžete spustit msvsmon z příkazového řádku se zjišťováním zakázané:  **Msvsmon /nodiscovery**.

## <a name="remote-debugger-ports-on-azure"></a>Porty vzdálené ladicí program v Azure
 Vzdálený ladicí program v Azure používá následující porty. Porty v cloudové službě jsou mapovány na porty konkrétního virtuálního počítače. Jsou všechny porty TCP.

|Připojení|Port v cloudové službě|Port ve virtuálním počítači|
|-|-|-|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarderx86|31401|31399|
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)