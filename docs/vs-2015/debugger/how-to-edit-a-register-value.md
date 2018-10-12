---
title: 'Postupy: Úprava hodnoty registru | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6846fc8ae093f3f63a0b9caceee7d0a0c23767f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49196154"
---
# <a name="how-to-edit-a-register-value"></a>Postupy: Úprava hodnoty registru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Okno registrů je k dispozici pouze v případě, že je povoleno ladění úrovni adres v **možnosti** dialogovém okně **ladění** uzlu.  
  
### <a name="to-change-the-value-of-a-register"></a>Chcete-li změnit hodnoty registru  
  
1.  V **zaregistruje** okno, použijte klávesu TAB nebo přesuňte kurzor myši přejděte k hodnotě, kterou chcete změnit. Když začnete psát, musí být kurzor umístěn před hodnota, kterou chcete přepsat.  
  
2.  Zadejte novou hodnotu.  
  
    > [!CAUTION]
    >  Změna hodnot registru (zejména v registrech EIP a EBP) může mít vliv na provádění programu.  
  
    > [!CAUTION]
    >  Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě neškodné úpravy mohou způsobit změny některých nejméně významných bitů v registru s plovoucí desetinnou čárkou.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití okna Registry](../debugger/how-to-use-the-registers-window.md)





