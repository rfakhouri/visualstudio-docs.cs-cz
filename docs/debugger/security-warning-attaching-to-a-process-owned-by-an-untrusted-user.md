---
title: 'Upozornění zabezpečení: Připojení k procesu vlastněnému nedůvěryhodným uživatelským může být nebezpečné. Pokud následující informace vypadají podezřele nebo si nejste jisti, nepřipojujte k tomuto procesu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22f7ecafbbf9c3d43c49d253bba482e0f2ff0941
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53821419"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>Upozornění zabezpečení: Připojení k procesu vlastněnému nedůvěryhodným uživatelským může být nebezpečné. Pokud následující údaje vypadají podezřele nebo si nejste jistí, k tomuto procesu se nepřipojujte.
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