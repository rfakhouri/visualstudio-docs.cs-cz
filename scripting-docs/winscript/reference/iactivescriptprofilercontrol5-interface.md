---
title: Iactivescriptprofilercontrol5 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7fd0ce34-6ae3-428f-ba90-3e86a8a98ed0
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b20afd05116a98e81a3eeea82e83e6ed200c44a
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349280"
---
# <a name="iactivescriptprofilercontrol5-interface"></a>IActiveScriptProfilerControl5 – rozhraní
Poskytuje metodu, jak vytvořit výčet objektů haldy GC spojených se skriptovacím modulem.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
interface IActiveScriptProfilerControl5 : IActiveScriptProfilerControl4  
```  
  
## <a name="methods"></a>Metody  
 [IActiveScriptProfilerControl5::EnumHeap2 – metoda](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)  
 Vrátí rozhraní ([iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)), který lze použít k iteraci objektů haldy GC v rámci přidruženého skriptovacího modulu.