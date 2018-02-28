---
title: "Postupy: Úprava hodnoty registru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.register.edit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b9cc839b7829070f5d4c2e9db9da12b6522c21eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-edit-a-register-value"></a>Postupy: Úprava hodnoty registru
Okna registry je k dispozici pouze v případě, že je povoleno ladění úrovni adresu v **možnosti** dialogové okno, **ladění** uzlu.  
  
### <a name="to-change-the-value-of-a-register"></a>Chcete-li změnit hodnotu registru  
  
1.  V **zaregistruje** okno, použijte klávesy TAB nebo přesuňte kurzor myši bod na hodnotu, kterou chcete změnit. Když začnete psát, musí být umístěn kurzor před hodnotu, kterou chcete přepsat.  
  
2.  Zadejte novou hodnotu.  
  
    > [!CAUTION]
    >  Změna hodnot registru (zejména v EIP a EBP Registry) může mít vliv na spuštění programu.  
  
    > [!CAUTION]
    >  Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě nepatrná upravit může způsobit změny k některým nejméně významný bity s plovoucí desetinnou čárkou registrace.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití okna registry](../debugger/how-to-use-the-registers-window.md)