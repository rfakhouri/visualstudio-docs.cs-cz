---
title: Idebugsessionprovider – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe73901d92cb42675ff9ec981bd9b90dcca5d546
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58148984"
---
# <a name="idebugsessionprovider-interface"></a>IDebugSessionProvider – rozhraní
Primární rozhraní poskytnuté ladicím programu integrované vývojové prostředí umožňující hostitele a jazyk zahájit ladění. Zjistí ladicí relace pro běžící aplikaci. Toto rozhraní je implementováno ladění správcem počítače.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugSessionProvider` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|Spustí relaci ladění pomocí zadané aplikace.|