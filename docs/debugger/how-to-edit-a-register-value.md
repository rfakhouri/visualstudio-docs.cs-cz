---
title: 'Postupy: Úprava hodnoty registru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a84cd75dd6ae6ecd2e62bd41ed384cd03305bbf0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963446"
---
# <a name="how-to-edit-a-register-value-c-c-visual-basic-f"></a>Postupy: Úprava hodnoty registru (C#, C++, Visual Basic, F#)

Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu.  
  
### <a name="to-change-the-value-of-a-register"></a>Chcete-li změnit hodnoty registru  
  
1.  V **zaregistruje** okno, použijte klávesu TAB nebo přesuňte kurzor myši přejděte k hodnotě, kterou chcete změnit. Když začnete psát, musí být kurzor umístěn před hodnota, kterou chcete přepsat.  
  
2.  Zadejte novou hodnotu.  
  
    > [!CAUTION]
    >  Změna hodnot registru (zejména v registrech EIP a EBP) může mít vliv na provádění programu.  
  
    > [!CAUTION]
    >  Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě neškodné úpravy mohou způsobit změny některých nejméně významných bitů v registru s plovoucí desetinnou čárkou.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití okna registry](../debugger/how-to-use-the-registers-window.md)