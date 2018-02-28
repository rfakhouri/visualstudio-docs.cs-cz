---
title: "Povolení Program chcete ladit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a581c5a9ae56f52727c011db1de2ad35a5ba3592
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-a-program-to-be-debugged"></a>Povolení Program chcete ladit
Předtím, než vaše ladění modulu (DE) můžete ladit program, musíte nejprve spusťte DE nebo jeho připojení k existující aplikaci.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Získání portu](../../extensibility/debugger/getting-a-port.md)  
 Popisuje, jak získat port jako první krok k povolení program chcete ladit.  
  
 [Registrace programu](../../extensibility/debugger/registering-the-program.md)  
 Vysvětluje, dalším kroku povolení program chcete ladit: registrace s port. Po registraci můžete ladit program buď proces připojení nebo ladění v běhu (JIT).  
  
 [Připojení k programu](../../extensibility/debugger/attaching-to-the-program.md)  
 Popisuje další krok: připojení k programu ladicího programu.  
  
 [Na základě spuštění připojení](../../extensibility/debugger/launch-based-attachment.md)  
 Popisuje spuštění na základě připojení k programu, který je automaticky při spuštění ve model SDM.  
  
 [Odesílání požadovaných událostí](../../extensibility/debugger/sending-the-required-events.md)  
 Vás provede požadované události při vytváření modul ladění (DE) a připojíte ho k programu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Definuje modul ladění (DE) a jsou popsány služby, které jsou implementovány pomocí rozhraní DE a jak může způsobit ladicí program na přechod mezi různé režimy provozu.