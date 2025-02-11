---
title: 'Postupy: Úprava hodnoty registru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7f0cd04b054d51119f6f6c1b0275c4f781656bff
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438305"
---
# <a name="how-to-edit-a-register-value"></a>Postupy: Úprava hodnoty registru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu.  
  
### <a name="to-change-the-value-of-a-register"></a>Chcete-li změnit hodnoty registru  
  
1. V **zaregistruje** okno, použijte klávesu TAB nebo přesuňte kurzor myši přejděte k hodnotě, kterou chcete změnit. Když začnete psát, musí být kurzor umístěn před hodnota, kterou chcete přepsat.  
  
2. Zadejte novou hodnotu.  
  
    > [!CAUTION]
    > Změna hodnot registru (zejména v registrech EIP a EBP) může mít vliv na provádění programu.  
  
    > [!CAUTION]
    > Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě neškodné úpravy mohou způsobit změny některých nejméně významných bitů v registru s plovoucí desetinnou čárkou.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití okna Registry](../debugger/how-to-use-the-registers-window.md)
