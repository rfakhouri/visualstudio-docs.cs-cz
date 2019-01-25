---
title: Implementace dodavatele portu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ffa6daa20c08bd236657c88e762b2f453554cb74
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755601"
---
# <a name="implementing-a-port-supplier"></a>Implementace dodavatele portu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Dodavatele portu poskytuje porty na požadavek na správce ladění relace (SDM). Dodavatele portu je potřeba implementovat při ladění na počítač bez modelu DCOM, nebo když musí podporovat nové zařízení. Například k poskytování ladění na mobilní telefon, může implementovat dodavatele portu, který poskytuje porty, které připojení k mobilním telefonu (možná prostřednictvím prostředí IR nebo buňky připojení) a vytváří výčet procesů a programy spuštěné na telefonu.  
  
 Ladění programů na počítače se systémem Windows (včetně vzdáleného ladění) Visual Studio poskytuje dodavatelé portů pro nativní a procesy Common Language Runtime (CLR), takže není nutné implementovat vlastní dodavatele portu v těchto případech.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace a registrace dodavatele portu](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 Tento článek popisuje, jak SDM komunikuje s dodavatele portu a jeho porty.  
  
 [Požadovaná rozhraní dodavatele portu](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Dokumenty rozhraní, které je třeba implementovat získat dodavatele portu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
