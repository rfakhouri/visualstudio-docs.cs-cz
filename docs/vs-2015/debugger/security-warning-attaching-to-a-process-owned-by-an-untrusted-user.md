---
title: 'Upozornění zabezpečení: Připojení k procesu, jehož vlastníkem je nedůvěryhodný uživatel, může být nebezpečné. Pokud následující informace vypadají podezřele nebo si nejste jisti, nepřipojujte k tomuto procesu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b856ac3a61d8af72d78546948bbe4ab780e9512e
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231144"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>Upozornění zabezpečení: Připojení k procesu, jehož vlastníkem je nedůvěryhodný uživatel, může být nebezpečné. Pokud následující údaje vypadají podezřele nebo si nejste jistí, k tomuto procesu se nepřipojujte.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upozornění zabezpečení: připojení k procesu vlastněnému nedůvěryhodným uživatelským může být nebezpečné. Pokud následující informace vypadají podezřele nebo si nejste jisti, nepřipojujte k tomuto procesu](https://docs.microsoft.com/visualstudio/debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process).  
  
Toto dialogové okno upozornění se zobrazí, když se připojíte k procesu, který obsahuje částečně důvěryhodným kódem, nebo je vlastníkem je nedůvěryhodný uživatel, okamžitě předtím, než dojde k připojení. Nedůvěryhodné proces, který obsahuje škodlivý kód má potenciál poškodit počítač ladění. Pokud máte důvod, proč nechtějí procesu, a pak kliknutím **zrušit** zabránit ladění.  
  
 Toto upozornění můžete potlačit při ladění legitimní scénáři, zavřete sadu Visual Studio a nastavte hodnotu tohoto klíče registru na 1: `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`a poté restartujte aplikaci Visual Studio. Po dokončení ladění scénář resetovat hodnotu na 0 a restartujte aplikaci Visual Studio.  
  
 "Důvěryhodných uživatelů" zahrnout sami a sada standardních uživatelů, kteří jsou obvykle definovány na počítačích, které mají rozhraní .NET Framework nainstalované, jako například `aspnet`, `localsystem`, `networkservice`, a `localservice`.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 Název  
 Název sestavení požadovaná pro ladění  
  
 Uživatel  
 Aktuální uživatel  
  
 Připojit  
 Stisknutím klávesy a pokračujte v ladění připojením  
  
 Nepřipojovat  
 Nepřipojujte se k procesu  
  
## <a name="see-also"></a>Viz také  
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)



