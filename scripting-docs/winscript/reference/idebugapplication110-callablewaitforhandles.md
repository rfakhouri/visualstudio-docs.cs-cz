---
title: IDebugApplication110::CallableWaitForHandles | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31802d8b86f007139959f3ece3bd1a0260599181
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54350021"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
Čeká na kterýkoli z úchytů zadané má být signalizován zároveň umožní volání mezi vlákny který se má publikovat pro toto vlákno. Tato metoda musí volat z vlákna ladicího programu.  
  
> [!IMPORTANT]
>  [Idebugapplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>Parametry  
 `handleCount`  
 Počet popisovačů čekání.  
  
 `pHandles`  
 Sada popisovače čekání.  
  
 `pIndex`  
 Pokud je hodnota HRESULT S_OK, budou indexovat `pHandles` pro popisovač, který byl signalizován.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md)