---
title: Implementace dodavatele Port | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: aa70e2a6019a97c248e6d4b411dacc222be59a1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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