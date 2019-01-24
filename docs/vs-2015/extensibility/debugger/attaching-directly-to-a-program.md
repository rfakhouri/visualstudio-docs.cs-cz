---
title: Připojení přímo k programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: ad2b7db8-821c-440c-ba07-c55c6a395e0f
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ab49163fc1474b541df3bc1b54d336574761baa3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788408"
---
# <a name="attaching-directly-to-a-program"></a>Připojení přímo k programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Uživatelé, kteří chtějí ladit programy v procesu, který je již spuštěna obvykle postupujte takto:  
  
1. V integrovaném vývojovém prostředí, zvolte **ladit procesy** příkaz **nástroje** nabídky.  
  
    **Procesy** zobrazí se dialogové okno.  
  
2. Vybrat proces a klikněte na tlačítko **připojit** tlačítko.  
  
    **Připojit k procesu** zobrazí se dialogové okno se seznamem všech ladicí stroj (DEs) na počítači nainstalovaný.  
  
3. Zadejte DEs používat k ladění procesu vybrané a potom klikněte na **OK**.  
  
   Ladit balíček spustí relaci ladění a předá seznam šifrování DEs. Relace ladění pak předá tento seznam, spolu s funkce zpětného volání, na vybraný proces a následně požádá procesu výčet jeho spuštěné programy.  
  
   V reakci na žádost uživatele prostřednictvím kódu programu, ladit balíček správce ladění relace (SDM) vytvoří instanci a předá seznam vybraných DEs. Společně se seznamem, předá ladit balíček SDM [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) rozhraní. Ladění balíčku předá seznam DEs vybraný proces voláním [IDebugProcess2::Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md). Pak zavolá SDM [IDebugProcess2::EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) na portu k vytvoření výčtu programů spuštěných v rámci procesu.  
  
   Od tohoto okamžiku každý ladicí stroj připojení k programu přesně podle popisu v [připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md), se dvěma výjimkami.  
  
   Z důvodu efektivity jsou seskupeny DEs, které jsou implementované sdílet adresní prostor s SDM tak, aby měl každý DE sadu programy, které se bude připojovat. V takovém případě [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) volání [IDebugEngine2::Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) a předává je pole programy se připojit k.  
  
   Druhou výjimkou je, že po spuštění události odeslané DE připojení k programu, který je již spuštěn, neobsahují obvykle událost vstupního bodu.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání událostí spuštění po spuštění](../../extensibility/debugger/sending-startup-events-after-a-launch.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)
