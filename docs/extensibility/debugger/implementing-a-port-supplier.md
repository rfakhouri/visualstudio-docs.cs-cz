---
title: Implementace dodavatele Port | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b0743f307dc579f6197880b0b89acaf2db0dda08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-a-port-supplier"></a>Implementace Port dodavatele
Port dodavatele poskytuje porty na žádost o správce ladicí relace (SDM). Port dodavatele musí implementovat při ladění do počítače bez modelu DCOM, nebo když nové zařízení musí být podporována. Zajistit ladění na mobilní telefon, například mohly implementovat dodavatele port, který poskytuje porty, které se připojují na mobilní telefon (možná prostřednictvím Reakcí nebo buňky připojení) a vytvoří výčet procesy a programy spuštěné na telefonu.  
  
 Ladění programů na počítačích se systémem Windows (včetně vzdálené ladění) Visual Studio poskytuje dodavatelé portu pro nativní a procesy Common Language Runtime (CLR), takže není nutné implementovat vlastní port dodavatele v těchto případech.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace a registrace dodavatele portu](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 Popisuje, jak SDM komunikuje s dodavatelem port a jeho porty.  
  
 [Požadovaná rozhraní dodavatele portu](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Dokumenty rozhraní, která musí být implementována získat port dodavatele.  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)