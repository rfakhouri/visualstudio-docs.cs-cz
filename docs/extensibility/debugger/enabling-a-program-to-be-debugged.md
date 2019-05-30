---
title: Povolení ladění programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b939b692e4e93243f5f346fcd2fcb2872e989615
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341634"
---
# <a name="enable-a-program-to-be-debugged"></a>Povolit program k ladění
Předtím, než vaše ladicího stroje (DE) můžete ladit program, musí nejdřív spustit DE nebo připojit k existující program.

## <a name="in-this-section"></a>V tomto oddílu
 [Získání portu](../../extensibility/debugger/getting-a-port.md) popisuje, jak získat port jako první krok k povolení ladění programu.

 [Registrovat program](../../extensibility/debugger/registering-the-program.md) vysvětluje povolení ladění programu na další krok: registrace s portem. Po registraci do programu můžete ladit buď tak, že proces připojení nebo ladění just-in-time (JIT).

 [Připojit k programu](../../extensibility/debugger/attaching-to-the-program.md) popisuje dál: připojování ladicího programu k programu.

 [Na základě spuštění připojení](../../extensibility/debugger/launch-based-attachment.md) popisuje přílohu spuštění programu, který je automaticky při spuštění pomocí SDM.

 [Odesílání požadovaných událostí](../../extensibility/debugger/sending-the-required-events.md) vás provede požadované události při vytváření ladicího stroje (DE) a připojení k programu.

## <a name="related-sections"></a>Související oddíly
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md) definuje ladicího stroje (DE) a jsou popsány služby implementované pomocí rozhraní DE a jak může způsobit přechod mezi různé provozní režimy ladicí program.