---
title: Idisperror – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDispError interface
ms.assetid: 3dc7b55e-94ba-4669-b20a-1e011f2d07cf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b717ebfe740a9b356513bb0f15e90c629a14e147
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345835"
---
# <a name="idisperror-interface"></a>IDispError – rozhraní
Poskytuje podrobné kontextové informace o chybě.  
  
> [!NOTE]
>  Toto rozhraní není implementováno.  
  
 Kromě metod zděděných z `IUnknown`, `IDispError` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDispError::QueryErrorInfo](../../winscript/reference/idisperror-queryerrorinfo.md)|Získá konkrétní typ informace o chybě.|  
|[IDispError::GetNext](../../winscript/reference/idisperror-getnext.md)|Načte další `IDispError` objektu.|  
|[IDispError::GetHresult](../../winscript/reference/idisperror-gethresult.md)|Získá kód chyby z `IDispError` objektu.|  
|[IDispError::GetSource](../../winscript/reference/idisperror-getsource.md)|Vrátí závislá na jazyku programový identifikátor pro třídu nebo aplikace, která vyvolala chybu.|  
|[IDispError::GetHelpInfo](../../winscript/reference/idisperror-gethelpinfo.md)|Vrátí cestu k souboru nápovědy a ID kontextu témat, která popisuje chybu, pokud je to možné.|  
|[IDispError::GetDescription](../../winscript/reference/idisperror-getdescription.md)|Vrátí textový popis chyby.|