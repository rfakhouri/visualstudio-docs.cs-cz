---
title: "Povolení Program chcete ladit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f1c38c110e9499936a24c33432180adf18209bf7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="enabling-a-program-to-be-debugged"></a>Povolení Program chcete ladit
Předtím, než vaše ladění modulu (DE) můžete ladit program, musíte nejprve spusťte DE nebo jeho připojení k existující aplikaci.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Získávání Port](../../extensibility/debugger/getting-a-port.md)  
 Popisuje, jak získat port jako první krok k povolení program chcete ladit.  
  
 [Registrace do programu](../../extensibility/debugger/registering-the-program.md)  
 Vysvětluje, dalším kroku povolení program chcete ladit: registrace s port. Po registraci můžete ladit program buď proces připojení nebo ladění v běhu (JIT).  
  
 [Připojení k programu](../../extensibility/debugger/attaching-to-the-program.md)  
 Popisuje další krok: připojení k programu ladicího programu.  
  
 [Na základě spuštění připojení](../../extensibility/debugger/launch-based-attachment.md)  
 Popisuje spuštění na základě připojení k programu, který je automaticky při spuštění ve model SDM.  
  
 [Odesílání požadované událostí](../../extensibility/debugger/sending-the-required-events.md)  
 Vás provede požadované události při vytváření modul ladění (DE) a připojíte ho k programu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytváření vlastních ladění modulu](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Definuje modul ladění (DE) a jsou popsány služby, které jsou implementovány pomocí rozhraní DE a jak může způsobit ladicí program na přechod mezi různé režimy provozu.