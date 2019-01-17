---
title: Idebugformatter – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugFormatter interface
ms.assetid: 022142d4-c8e1-47ae-b771-3e24953293e5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 353a85ab51252c92086fa478d95b2e29ab3db62d
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348032"
---
# <a name="idebugformatter-interface"></a>IDebugFormatter – rozhraní
Umožňuje jazyk nebo integrované vývojové prostředí přizpůsobit převod mezi hodnotami VARIANT nebo VARTYPE typy a řetězci.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugFormatter` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugFormatter::GetStringForVariant](../../winscript/reference/idebugformatter-getstringforvariant.md)|Vrátí řetězec, který představuje dané hodnoty hodnotu typu VARIANT.|  
|[IDebugFormatter::GetVariantForString](../../winscript/reference/idebugformatter-getvariantforstring.md)|Vrátí hodnotu typu VARIANT obsahující daný řetězec.|  
|[IDebugFormatter::GetStringForVarType](../../winscript/reference/idebugformatter-getstringforvartype.md)|Vrátí řetězec, který představuje dané hodnota VARTYPE.|