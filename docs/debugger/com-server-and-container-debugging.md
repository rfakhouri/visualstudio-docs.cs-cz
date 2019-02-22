---
title: Ladění modelu COM serveru a kontejneru | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- COM servers, debugging
- ActiveX controls, debugging
- COM [Visual Studio], debugging
ms.assetid: b7ce8696-ebb8-4354-a767-f76b8ada4ac1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 104af46114da44d3d4a4348e760bd24a2aab5412
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602049"
---
# <a name="com-server-and-container-debugging"></a>Ladění serveru a kontejneru modelu COM
Aplikace modelu COM provést několik úloh mimo přímou kontrolu programátora. Komunikace mezi knihovny DLL, využití se počítá na objekty a operace se schránkou je uvedeno několik oblastí, kde může dojít k neočekávanému chování. Pokud k tomu dojde, prvním krokem je sledovat příčiny problému.

 Ladicí program sady Visual Studio podporuje krokování přes a kontejnery a servery. To zahrnuje možnost Krokovat přes Vzdálená volání procedur (RPC).

##  <a name="BKMK_COMServerandContainerintheSameSolution"></a> Ladění modelu COM serveru a kontejneru ve stejném řešení
 Můžete ladit serveru COM a kontejner pomocí dva projekty ve stejném řešení. Nastavte odpovídající zarážky v každém projektu a ladění. Když kontejneru zavolá do serveru, na kterém narazí na zarážku, kontejner počká, až do kódu serveru vrátí (až dokončíte její ladění).

 Ladění kontejnerů COM je podobné ladění standardní program. Jedním rozdílem je, když ladíte událost, která generuje zpětné volání (například přetažení dat přes aplikace typu kontejner). V takovém případě musíte nastavit zarážku ve funkci zpětného volání.

##  <a name="BKMK_ServerApplicationWithoutContainerInformation"></a> Ladění aplikace serveru bez informací o kontejneru
 Pokud nemají nebo nechcete používat informace o ladění pro svou aplikaci typu kontejner, spouští se ladění aplikace je třech krocích:

1.  Spusťte ladění na server jako normální aplikace.

2.  Nastavte zarážky podle potřeby.

3.  Spuštění aplikace typu kontejner.

##  <a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a> Ladění serveru a domény izolace (SDI) aplikace
 Pokud ladíte aplikace serveru SDI, je nutné zadat `/Embedding` nebo `/Automation` v **argumenty příkazového řádku** vlastnost *projektu* dialogové okno stránky vlastností pro C/C++, C#, nebo Projekty Visual Basic.

 S těmito argumenty příkazového řádku můžete ladicí program spuštění serverové aplikace, jako by byly spuštěny z kontejneru. Kontejner od programový manažer nebo správce souborového poté způsobí kontejneru pro použití instance serveru spuštěného v ladicím programu.

 Pro přístup *projektu* dialogové okno stránky vlastností, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a v místní nabídce zvolte možnost Vlastnosti. Pokud chcete najít vlastnost argumenty příkazového řádku, rozbalte kategorii vlastnosti konfigurace a klikněte na stránce ladění.

## <a name="see-also"></a>Viz také

- [Ladění modelů COM a prvků ActiveX](../debugger/com-and-activex-debugging.md)