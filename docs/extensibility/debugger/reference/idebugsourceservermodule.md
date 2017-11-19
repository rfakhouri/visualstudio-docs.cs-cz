---
title: IDebugSourceServerModule | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugSourceServerModule interface
ms.assetid: 38213060-451d-46e6-8b4a-efc123e01a2c
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa50dcd0e379b3e32c11d531db25817038ed9c65
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugsourceservermodule"></a>IDebugSourceServerModule
Představuje informace o zdrojovém serveru, obsažené v souboru PDB.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugSourceServerModule : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementované moduly ladicího programu a spotřebovávají ladicí program uživatelského rozhraní.  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `IDebugSourceServerModule`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getsourceserverdata –](../../../extensibility/debugger/reference/idebugsourceservermodule-getsourceserverdata.md)|Načte pole informace o zdrojovém serveru.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll