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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 58094d505cf2fd3621b801040f0f71904796d86b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388424"
---
# <a name="how-to-edit-a-register-value-c-c-visual-basic-f"></a>Postupy: Úprava hodnoty registru (C#, C++, Visual Basic, F#)

Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu.

### <a name="to-change-the-value-of-a-register"></a>Chcete-li změnit hodnoty registru

1. V **zaregistruje** okno, použijte klávesu TAB nebo přesuňte kurzor myši přejděte k hodnotě, kterou chcete změnit. Když začnete psát, musí být kurzor umístěn před hodnota, kterou chcete přepsat.

2. Zadejte novou hodnotu.

    > [!CAUTION]
    > Změna hodnot registru (zejména v registrech EIP a EBP) může mít vliv na provádění programu.

    > [!CAUTION]
    > Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě neškodné úpravy mohou způsobit změny některých nejméně významných bitů v registru s plovoucí desetinnou čárkou.

## <a name="see-also"></a>Viz také
- [Postupy: Použití okna Registry](../debugger/how-to-use-the-registers-window.md)