---
title: Připojení přímo k Program | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: ad2b7db8-821c-440c-ba07-c55c6a395e0f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6885cb0dea801ab95e2e88e3f8168c139fea0e0c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100374"
---
# <a name="attaching-directly-to-a-program"></a>Připojení přímo k programu
Uživatelé, kteří chtějí k ladění programů v procesu, který je již spuštěn obvykle postupujte takto:  
  
1.  V prostředí IDE, vyberte **ladění procesy** příkaz **nástroje** nabídky.  
  
     **Procesy** zobrazí se dialogové okno.  
  
2.  Vybrat proces a klikněte na **Attach** tlačítko.  
  
     **Připojit k procesu** zobrazí se dialogové okno se seznamem všech ladění moduly (DEs) v počítači nainstalován.  
  
3.  Zadejte DEs sloužící k ladění proces vybrané a potom klikněte na **OK**.  
  
 Ladění balíček spustí relaci ladění a předá ho seznam šifrování DEs. Relaci ladění pak předá tento seznam, společně s funkci zpětného volání, do procesu vybrané a následně požádá proces výčet jeho spuštěné programy.  
  
 V reakci na žádost uživatele prostřednictvím kódu programu, balíček ladění vytvoří správce ladicí relace (SDM) a předá ho seznam vybraných DEs. Společně s seznamu předá ladění balíček SDM [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) rozhraní. Seznam DEs proces vybraný balíček ladění předá voláním [IDebugProcess2::Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md). Pak zavolá SDM [IDebugProcess2::EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) na portu výčet programům spuštěným v procesu.  
  
 Z tohoto bodu na každý motor ladění je připojen k program přesně podle popisu v [připojení po spusťte](../../extensibility/debugger/attaching-after-a-launch.md), se dvěma výjimkami.  
  
 Pro efektivitu jsou seskupené DEs, které jsou implementované sdílet adresní prostor s SDM tak, aby každý DE obsahuje sadu programů, které se připojí se k. V takovém případě [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) volání [IDebugEngine2::Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) a předává je pole programů pro připojení k.  
  
 Druhou výjimkou je, že události spuštění poslal Zavedenými připojení k programu, který je již spuštěna obvykle neobsahují události vstupní bod.  
  
## <a name="see-also"></a>Viz také  
 [Odesílání událostí spuštění po spuštění](../../extensibility/debugger/sending-startup-events-after-a-launch.md)   
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)