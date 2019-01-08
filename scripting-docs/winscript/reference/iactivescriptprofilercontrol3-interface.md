---
title: Iactivescriptprofilercontrol3 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 64bc860a-54d4-475a-80f6-2f9dba6448ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bebe351608b3136ac00a059bffab3535141e7fca
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097133"
---
# <a name="iactivescriptprofilercontrol3-interface"></a>IActiveScriptProfilerControl3 – rozhraní
Poskytuje metodu, jak vytvořit výčet objektů haldy GC spojených se skriptovacím modulem.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
interface IActiveScriptProfilerControl3 : IActiveScriptProfilerControl2  
```  
  
## <a name="methods"></a>Metody  
 [IActiveScriptProfilerControl3::EnumHeap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)  
 Vrátí rozhraní ([iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)), který lze použít k iteraci objektů haldy GC v rámci přidruženého skriptovacího modulu.